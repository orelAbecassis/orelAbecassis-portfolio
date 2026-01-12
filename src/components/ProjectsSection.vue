<script setup lang="ts">
import { ref, onMounted, nextTick, computed } from 'vue'

// === ÉTAT DU COMPOSANT ===
const projetsDev = ref<any[]>([])
const projetsCommunity = ref<any[]>([])
const isLoading = ref(true)
const error = ref<string | null>(null)
const selectedProject = ref<any | null>(null)
const isModalOpen = ref(false)
const currentImageIndex = ref(0)

// === PROPRIÉTÉS CALCULÉES ===
const currentImage = computed(() => {
  if (selectedProject.value?.images?.length) {
    return selectedProject.value.images[currentImageIndex.value]
  }
  return selectedProject.value?.image || ''
})

const hasMultipleImages = computed(() => 
  selectedProject.value?.images?.length > 1
)

// === CHARGEMENT INITIAL ===
onMounted(async () => {
  // 1. Récupération des projets depuis l'API
  try {
    const res = await fetch('http://localhost:3000/api/projects')
    if (!res.ok) throw new Error('Serveur backend non accessible sur le port 3000')
    
    const data = await res.json()
    // 2. Séparation par type de projet
    projetsDev.value = data.filter((p: any) => p.type === 'Dev')
    projetsCommunity.value = data.filter((p: any) => p.type === 'Community management')
  } catch (err: any) {
    error.value = err.message
  } finally {
    isLoading.value = false
  }

  // 3. Animation d'apparition au scroll
  await nextTick()
  const observer = new IntersectionObserver(
    (entries) => entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible')
        observer.unobserve(entry.target)
      }
    }),
    { threshold: 0.15 }
  )
  document.querySelectorAll('.fade').forEach((el) => observer.observe(el))
})

// === GESTION DE LA MODALE ===
const fetchProjectDetails = async (id: string) => {
  try {
    const res = await fetch(`http://localhost:3000/api/projects/${id}`)
    if (!res.ok) throw new Error('Erreur lors du chargement du projet')
    
    selectedProject.value = await res.json()
    currentImageIndex.value = 0
    isModalOpen.value = true
    document.addEventListener('keydown', handleKeydown)
  } catch (err: any) {
    error.value = err.message
  }
}

const closeModal = () => {
  isModalOpen.value = false
  selectedProject.value = null
  currentImageIndex.value = 0
  document.removeEventListener('keydown', handleKeydown)
}

// === NAVIGATION DANS LES IMAGES ===
const nextImage = () => {
  const totalImages = selectedProject.value?.images?.length || 0
  if (totalImages > 1) {
    currentImageIndex.value = (currentImageIndex.value + 1) % totalImages
  }
}

const previousImage = () => {
  const totalImages = selectedProject.value?.images?.length || 0
  if (totalImages > 1) {
    currentImageIndex.value = currentImageIndex.value === 0 
      ? totalImages - 1 
      : currentImageIndex.value - 1
  }
}

// === NAVIGATION CLAVIER ===
const handleKeydown = (event: KeyboardEvent) => {
  if (!isModalOpen.value) return
  
  if (event.key === 'ArrowLeft') previousImage()
  else if (event.key === 'ArrowRight') nextImage()
  else if (event.key === 'Escape') closeModal()
  
  event.preventDefault()
}
</script>

<template>
  <section id="projects" class="min-h-screen bg-gradient-to-br from-purple-300 via-pink-200 to-indigo-100 pt-20 px-4 sm:px-6 lg:px-8">
    <div class="max-w-7xl mx-auto">
      <h1 class="text-4xl font-bold text-center text-purple-700 mb-12">Mes Projets</h1>

      <div v-if="isLoading" class="text-center text-gray-600">
        <p>Chargement des projets...</p>
      </div>

      <div v-else-if="error" class="text-center text-red-600 bg-red-100 p-4 rounded-lg">
        <p>Une erreur est survenue : {{ error }}</p>
      </div>

      <div v-else>
        <h2 class="text-2xl font-bold text-purple-800 mb-6">Mes Projets Développement</h2>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 mb-12">
          <component
            v-for="p in projetsDev"
            :is="p.tags && p.tags.includes('En Ligne') && p.url ? 'a' : 'div'"
            :href="p.tags && p.tags.includes('En Ligne') && p.url ? p.url : undefined"
            target="_blank"
            rel="noopener"
            :key="p.id"
            class="fade bg-white/70 rounded-xl shadow-lg overflow-hidden transition-all duration-300 hover:scale-105 hover:shadow-2xl border-2 border-purple-200 hover:border-purple-400 cursor-pointer backdrop-blur-sm"
            @click="!p.tags || !p.tags.includes('En Ligne') || !p.url ? fetchProjectDetails(p.id) : null"
          >
            <img v-if="p.image" :src="p.image" :alt="p.name" class="w-full h-48 object-cover" />
            <div v-else class="w-full h-48 bg-gray-200/50 flex items-center justify-center">
              <span class="text-gray-500">Image non disponible</span>
            </div>
            <div class="p-6">
              <h2 class="text-xl font-semibold text-purple-800 text-center">{{ p.name }}</h2>
            </div>
          </component>
        </div>

        <h2 class="text-2xl font-bold text-purple-800 mb-6">Mes Projets Community Management</h2>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 mb-12">
          <component
            v-for="p in projetsCommunity"
            :is="p.tags && p.tags.includes('En Ligne') && p.url ? 'a' : 'div'"
            :href="p.tags && p.tags.includes('En Ligne') && p.url ? p.url : undefined"
            target="_blank"
            rel="noopener"
            :key="p.id"
            class="fade bg-white/70 rounded-xl shadow-lg overflow-hidden transition-all duration-300 hover:scale-105 hover:shadow-2xl border-2 border-purple-200 hover:border-purple-400 cursor-pointer backdrop-blur-sm"
            @click="!p.tags || !p.tags.includes('En Ligne') || !p.url ? fetchProjectDetails(p.id) : null"
          >
            <img v-if="p.image" :src="p.image" :alt="p.name" class="w-full h-48 object-cover" />
            <div v-else class="w-full h-48 bg-gray-200/50 flex items-center justify-center">
              <span class="text-gray-500">Image non disponible</span>
            </div>
            <div class="p-6">
              <h2 class="text-xl font-semibold text-purple-800 text-center">{{ p.name }}</h2>
            </div>
          </component>
        </div>
      </div>

      <!-- Modale -->
      <div
        v-if="isModalOpen"
        class="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-50"
        @click.self="closeModal"
      >
        <div
          class="relative bg-white rounded-xl shadow-2xl max-w-4xl w-full h-[600px] p-8 animate-fadeIn flex flex-col"
        >
          <button
            class="absolute top-4 right-4 text-3xl text-gray-400 hover:text-purple-600 font-bold z-10"
            @click="closeModal"
          >
            ×
          </button>

          <div v-if="selectedProject" class="flex-1 flex flex-col">
            <h2 class="text-2xl font-bold text-purple-800 mb-4 text-center">
              {{ selectedProject.name }}
            </h2>

            <div class="relative flex-1 flex items-center justify-center mb-4">
              <!-- Affichage de l'image avec carrousel -->
              <div v-if="currentImage" class="relative w-full h-full flex items-center justify-center">
                <!-- Bouton Précédent -->
                <button
                  v-if="hasMultipleImages"
                  @click="previousImage"
                  class="absolute left-4 top-1/2 -translate-y-1/2 z-20 bg-white hover:bg-gray-100 rounded-full p-3 shadow-lg transition-all hover:scale-110 border-2 border-purple-200"
                >
                  <svg class="w-6 h-6 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                  </svg>
                </button>

                <!-- Image principale -->
                <img
                  :src="currentImage"
                  :alt="selectedProject.name"
                  class="max-h-80 max-w-full object-contain rounded-lg shadow-lg transition-all duration-300"
                />

                <!-- Bouton Suivant -->
                <button
                  v-if="hasMultipleImages"
                  @click="nextImage"
                  class="absolute right-4 top-1/2 -translate-y-1/2 z-20 bg-white hover:bg-gray-100 rounded-full p-3 shadow-lg transition-all hover:scale-110 border-2 border-purple-200"
                >
                  <svg class="w-6 h-6 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                  </svg>
                </button>

                <!-- Compteur d'images -->
                <div
                  v-if="hasMultipleImages"
                  class="absolute bottom-4 left-1/2 -translate-x-1/2 bg-black/50 text-white px-3 py-1 rounded-full text-sm"
                >
                  {{ currentImageIndex + 1 }} / {{ selectedProject.images.length }}
                </div>
              </div>

              <div v-else class="text-gray-400">Aucune image disponible</div>
            </div>

            <div v-if="selectedProject.description" class="text-gray-700 text-lg mb-4 text-center">
              {{ selectedProject.description }}
            </div>
            <div v-else class="text-gray-400 text-center">Aucune description disponible.</div>
          </div>

          <div v-else class="text-center text-gray-400">Chargement...</div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Animation d'apparition au scroll */
.fade {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}

.fade.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Animation d'ouverture de la modale */
@keyframes fadeIn {
  from { 
    opacity: 0; 
    transform: scale(0.95); 
  }
  to { 
    opacity: 1; 
    transform: scale(1); 
  }
}

.animate-fadeIn { 
  animation: fadeIn 0.2s ease; 
}
</style>
