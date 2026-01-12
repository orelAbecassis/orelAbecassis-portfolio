<template>
  <div class="relative min-h-screen flex">
    <!-- Colonne gauche violette (35%) -->
    <div class="w-[35%] bg-gradient-to-br from-purple-600 to-purple-200 relative flex flex-col">
      <img
        src="../Images/logo_ABEWEB.png"
        alt="Logo Abweb"
        class="absolute top-8 left-8 w-64 h-auto z-20"
      />
    </div>

    <!-- Colonne droite blanche (65%) -->
    <div class="w-[65%] bg-white relative flex flex-col justify-between">
      <div class="flex flex-col justify-center h-full pl-[420px] pr-16">
        <!-- Animation lettre par lettre -->
        <div class="text-2xl text-purple-500 font-semibold mb-4 min-h-[40px] flex items-center">
          <span>{{ displayedRole }}</span><span v-if="showCursor" class="text-purple-700">|</span>
        </div>

        <!-- Nom -->
        <h1 class="text-8xl font-black text-gray-900 mb-6">Orel Abecassis</h1>

        <!-- Texte descriptif -->
        <p class="text-xl text-gray-600 mb-12 max-w-2xl">
          Développeur web passionné par la création d'expériences numériques élégantes et performantes.
          Toujours prêt à relever de nouveaux défis et à apprendre de nouvelles technologies.
        </p>

        <!-- BADGES RESEAUX -->
        <div class="flex items-center gap-4">
          <a href="https://www.linkedin.com/in/orel-abecassis-488ba7203/" target="_blank" rel="noopener">
            <img
              src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"
              alt="LinkedIn"
              class="h-10"
            />
          </a>
          <a href="https://discordapp.com/users/775785441198211113" target="_blank" rel="noopener">
            <img
              src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white"
              alt="Discord"
              class="h-10"
            />
          </a>
          <a href="https://github.com/orelAbecassis" target="_blank" rel="noopener">
            <img
              src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"
              alt="GitHub"
              class="h-10"
            />
          </a>
        </div>
      </div>
    </div>

    <!-- Photo ronde -->
    <div class="absolute top-1/2 left-[35%] -translate-x-1/2 -translate-y-1/2 z-20">
      <img
        :src="photoOrel"
        alt="Orel Abecassis"
        class="rounded-full border-8 border-white shadow-2xl w-[550px] h-[550px] object-cover"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import photoOrel from '../Images/photo-orel.jpeg'

const roles = ['Développeur Full Stack', 'Cheffe de projet', 'Freelance Tech']
const currentIndex = ref(0)
const displayedRole = ref('')
const showCursor = ref(true)

let letterIndex = 0
let typingInterval: number
let roleInterval: number
let cursorInterval: number

function typeRole() {
  displayedRole.value = ''
  letterIndex = 0
  clearInterval(typingInterval)
  typingInterval = setInterval(() => {
    if (letterIndex < roles[currentIndex.value].length) {
      displayedRole.value += roles[currentIndex.value][letterIndex]
      letterIndex++
    } else {
      clearInterval(typingInterval)
      roleInterval = setTimeout(() => {
        currentIndex.value = (currentIndex.value + 1) % roles.length
        typeRole()
      }, 2000)
    }
  }, 60)
}

onMounted(() => {
  typeRole()
  cursorInterval = setInterval(() => {
    showCursor.value = !showCursor.value
  }, 500)

  // 🎬 Animation au scroll sur les projets uniquement
  const elements = document.querySelectorAll('.fade')
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible')
        }
      })
    },
    { threshold: 0.15 }
  )
  elements.forEach((el) => observer.observe(el))
})

onUnmounted(() => {
  clearInterval(typingInterval)
  clearTimeout(roleInterval)
  clearInterval(cursorInterval)
})
</script>

<style scoped>
.fade {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}
.fade.visible {
  opacity: 1;
  transform: translateY(0);
}
</style>
