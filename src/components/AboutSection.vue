<template>
  <section
    id="about"
    class="flex flex-col items-center justify-start min-h-screen bg-gradient-to-br from-purple-100 via-purple-50 to-white pt-20 px-4">
    <div class="flex flex-col items-center w-full">
      <!-- 🧍‍♀️ Titre -->
      <h1 class="fade text-5xl font-bold text-purple-700 mb-6 drop-shadow-sm">À propos de moi</h1>

      <!-- 📝 Texte principal -->
      <div class="fade max-w-6xl w-full text-center text-lg text-gray-800 mb-8">
        <h2 class="text-3xl font-bold text-purple-600 mb-6">Qui suis-je&nbsp;?</h2>

        <p class="mb-2">
          Je suis <span class="font-bold">Orel Abecassis</span>, cheffe de projet et développeuse web passionnée par
          l'innovation numérique et les nouvelles technologies.
        </p>

        <p class="mb-2">
          J'ai obtenu un <span class="font-bold">Bac+5 en informatique</span>, spécialisé en développement web et gestion
          de projet, et je poursuis aujourd'hui un <span class="font-bold">double master en entrepreneuriat</span> afin
          de renforcer mes compétences en management, stratégie et leadership.
        </p>

        <p class="mb-2">
          Passionnée par le <span class="font-bold">DevOps</span>, la <span class="font-bold">gestion de projet</span> et
          le <span class="font-bold">développement web</span>, j'ai choisi de me lancer en
          <span class="font-bold">freelance</span> pour me consacrer pleinement à mes passions :
          <span class="text-purple-600 font-semibold">créer, automatiser et piloter des projets innovants</span>.
        </p>

        <p class="mb-2">
          Je suis également <span class="font-bold">community manager</span>, en charge de la gestion et de la mise en
          valeur de plusieurs comptes Instagram.
        </p>

        <!-- 🔗 Bouton -->
        <div class="my-6">
          <a href="#projects">
            <button
              class="px-8 py-3 bg-purple-600 text-white rounded-lg shadow-md hover:shadow-lg hover:bg-purple-700 transition-all duration-300 font-semibold text-base"
            >
              Voir mes projets
            </button>
          </a>
        </div>

        <p>
          Ma double expertise en développement et en gestion de projet me permet d'accompagner mes clients de la
          conception à la réalisation de leurs projets numériques, en garantissant des solutions techniques innovantes
          et adaptées à leurs besoins.
        </p>
      </div>

      <!-- 💻 Compétences -->
   <div class="w-full max-w-6xl">
          <h2 class="text-3xl font-bold text-purple-700 mb-6">Compétences techniques</h2>
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mb-8">
            <!-- Langages -->
            <div class="bg-white rounded-xl shadow-md p-6 flex flex-col items-center border border-purple-200 transition-all duration-300 hover:shadow-xl hover:border-purple-400 cursor-pointer">
              <h3 class="font-bold text-purple-700 mb-4 text-xl flex items-center gap-2">
                <span>Langages</span>
              </h3>
              <div class="flex flex-wrap gap-4 justify-center">
                <!-- HTML -->
                <div class="flex flex-col items-center">
                  <i class="devicon-html5-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">HTML</span>
                </div>
                <!-- CSS -->
                <div class="flex flex-col items-center">
                  <i class="devicon-css3-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">CSS</span>
                </div>
                <!-- PHP -->
                <div class="flex flex-col items-center">
                  <i class="devicon-php-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">PHP</span>
                </div>
            
                <!-- Python -->
                <div class="flex flex-col items-center">
                  <i class="devicon-python-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">Python</span>
                </div>
              </div>
            </div>
            <!-- Outils -->
            <div class="bg-white rounded-xl shadow-md p-6 flex flex-col items-center border border-purple-200 transition-all duration-300 hover:shadow-xl hover:border-purple-400 cursor-pointer">
              <h3 class="font-bold text-purple-700 mb-4 text-xl flex items-center gap-2">
                <span>Outils</span>
              </h3>
              <div class="flex flex-wrap gap-4 justify-center">
                <!-- Git -->
                <div class="flex flex-col items-center">
                  <i class="devicon-git-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">Git</span>
                </div>
                <!-- GitHub -->
                <div class="flex flex-col items-center">
                  <i class="devicon-github-original colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">GitHub</span>
                </div>
                    <!-- Docker -->
                <div class="flex flex-col items-center">
                  <img src="../Images/logo_skills/docker.png" alt="Docker" class="h-12 w-12 aspect-square object-contain bg-white rounded p-1 mx-auto shadow" />
                  <span class="text-xs mt-1">Docker</span>
                </div>
                     <!-- Jenkins-->
                <div class="flex flex-col items-center">
                  <img src="../Images/logo_skills/Jenkins_logo.png" alt="Jenkins" class="h-12 w-12 aspect-square object-contain bg-white rounded p-1 mx-auto shadow" />
                  <span class="text-xs mt-1">Jenkins</span>
                </div>
                <!-- VSCode -->
                <div class="flex flex-col items-center">
                  <i class="devicon-vscode-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">VSCode</span>
                </div>
                <!-- PyCharm -->
                <div class="flex flex-col items-center">
                  <i class="devicon-pycharm-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">PyCharm</span>
                </div>
            
                <!-- Grafana -->
                <div class="flex flex-col items-center">
                  <img src="../Images/logo_skills/grafana.png" alt="Grafana" class="h-12 w-12 aspect-square object-contain bg-white rounded p-1 mx-auto shadow" />
                  <span class="text-xs mt-1">Grafana</span>
                </div>
                    <!-- Microsoft 365 -->
                <div class="flex flex-col items-center">
                  <img src="../Images/logo_skills/Microsoft.png" alt="Microsoft 365" class="h-12 w-12 aspect-square object-contain bg-white rounded p-1 mx-auto shadow" />
                  <span class="text-xs mt-1">Microsoft 365</span>
                </div>
              </div>
            </div>
           
            <!-- Systèmes d'exploitation -->
            <div class="bg-white rounded-xl shadow-md p-6 flex flex-col items-center border border-purple-200 transition-all duration-300 hover:shadow-xl hover:border-purple-400 cursor-pointer">
              <h3 class="font-bold text-purple-700 mb-4 text-xl flex items-center gap-2">
                <span>Systèmes d'exploitation</span>
              </h3>
              <div class="flex flex-wrap gap-4 justify-center">
                <!-- Windows -->
                <div class="flex flex-col items-center">
                  <img src="../Images/logo_skills/windows_logo.webp" alt="Windows" class="h-12 w-12 aspect-square object-contain bg-white rounded p-1 mx-auto shadow" />
                  <span class="text-xs mt-1">Windows</span>
                </div>
                <!-- Red Hat -->
                <div class="flex flex-col items-center">
                  <i class="devicon-redhat-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">Red Hat</span>
                </div>
                <!-- Linux -->
                <div class="flex flex-col items-center">
                  <i class="devicon-linux-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">Linux</span>
                </div>
              </div>
            </div>
            <!-- Bases de données -->
            <div class="bg-white rounded-xl shadow-md p-6 flex flex-col items-center border border-purple-200 transition-all duration-300 hover:shadow-xl hover:border-purple-400 cursor-pointer">
              <h3 class="font-bold text-purple-700 mb-4 text-xl flex items-center gap-2">
                <span>Bases de données</span>
              </h3>
              <div class="flex flex-wrap gap-4 justify-center">
                <!-- MySQL -->
                <div class="flex flex-col items-center">
                  <i class="devicon-mysql-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">MySQL</span>
                </div>
                <!-- Oracle -->
                <div class="flex flex-col items-center">
                  <i class="devicon-oracle-original colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">Oracle</span>
                </div>
                <!-- MariaDB -->
                <div class="flex flex-col items-center">
                  <i class="devicon-mariadb-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">MariaDB</span>
                </div>
                <!-- PostgreSQL -->
                <div class="flex flex-col items-center">
                  <i class="devicon-postgresql-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">PostgreSQL</span>
                </div>
                <!-- Druid -->
                <div class="flex flex-col items-center">
                  <img src="../Images/logo_skills/druid.png" alt="Druid" class="h-12 w-12 aspect-square object-contain bg-white rounded p-1 mx-auto shadow" />
                  <span class="text-xs mt-1">Druid</span>
                </div>
              </div>
            </div>
             <!-- CMS -->
            <div class="bg-white rounded-xl shadow-md p-6 flex flex-col items-center border border-purple-200 transition-all duration-300 hover:shadow-xl hover:border-purple-400 cursor-pointer">
              <h3 class="font-bold text-purple-700 mb-4 text-xl flex items-center gap-2">
                <span>CMS</span>
              </h3>
              <div class="flex flex-wrap gap-4 justify-center">
                <!-- Odoo -->
                <div class="flex flex-col items-center">
                  <img src="../Images/logo_skills/Odoo-Logo.wine.png" alt="Odoo" class="h-12 w-12 aspect-square object-contain bg-white rounded p-1 mx-auto shadow" />
                  <span class="text-xs mt-1">Odoo</span>
                </div>
                <!-- WordPress -->
                <div class="flex flex-col items-center">
                  <i class="devicon-wordpress-plain colored text-4xl bg-white rounded p-1 aspect-square mx-auto shadow" style="width:3rem;height:3rem;display:flex;align-items:center;justify-content:center;"></i>
                  <span class="text-xs mt-1">WordPress</span>
                </div>
              </div>
            </div>
          </div>

      <!-- 🧭 Parcours -->
       <h2 class="text-3xl font-bold text-purple-700 mb-6">Parcours</h2>
          <ol class="relative border-l-4 border-purple-300 ml-4">
                  <li class="mb-8 ml-6 p-5 rounded-lg transition-all duration-300 hover:bg-white/80 hover:shadow-md cursor-pointer">
              <span class="absolute -left-4 flex items-center justify-center w-8 h-8 bg-purple-600 rounded-full ring-4 ring-white text-white font-bold shadow-md text-sm">1</span>
              <h3 class="font-bold text-lg text-gray-800">Master en entrepreneuriat - Alternance à la Société Générale</h3>
              <div class="text-gray-600">Ort Montreuil Daniel Mayer - 3IL</div>
              <time class="block mb-1 text-sm font-normal leading-none text-gray-400">2023 - 2025</time>
            </li>

            <li class="mb-8 ml-6 p-5 rounded-lg transition-all duration-300 hover:bg-white/80 hover:shadow-md cursor-pointer">
              <span class="absolute -left-4 flex items-center justify-center w-8 h-8 bg-purple-500 rounded-full ring-4 ring-white text-white font-bold shadow-md text-sm">2</span>
              <h3 class="font-bold text-lg text-gray-800">Master en Manager des Solutions Digitals et Data (MSD2) - Alternance à la Société Générale</h3>
              <div class="text-gray-600">Ort Montreuil Daniel Mayer - 3IL</div>
              <time class="block mb-1 text-sm font-normal leading-none text-gray-400">2023 - 2025</time>
            </li>

            <li class="mb-8 ml-6 p-5 rounded-lg transition-all duration-300 hover:bg-white/80 hover:shadow-md cursor-pointer">
              <span class="absolute -left-4 flex items-center justify-center w-8 h-8 bg-purple-400 rounded-full ring-4 ring-white text-white font-bold shadow-md text-sm">3</span>
              <h3 class="font-bold text-lg text-gray-800">Bachelor Conception des systèmes informatique en développement - Alternance dans un cabinet d'expertise comptable Delph Fiduciaire</h3>
              <div class="text-gray-600">Ort Montreuil Daniel Mayer</div>
              <time class="block mb-1 text-sm font-normal leading-none text-gray-400">2022 - 2023</time>
            </li>

            <li class="mb-8 ml-6 p-5 rounded-lg transition-all duration-300 hover:bg-white/80 hover:shadow-md cursor-pointer">
              <span class="absolute -left-4 flex items-center justify-center w-8 h-8 bg-purple-300 rounded-full ring-4 ring-white text-white font-bold shadow-md text-sm">4</span>
              <h3 class="font-bold text-lg text-gray-800">BTS Service Informatique aux Organisation (SIO) Option SLAM</h3>
              <div class="text-gray-600">Ort Montreuil Daniel Mayer</div>
              <time class="block mb-1 text-sm font-normal leading-none text-gray-400">2020 - 2022</time>
            </li>
          </ol>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { onMounted, nextTick } from 'vue'
import 'devicon/devicon.min.css'

const parcours = [
  {
    titre: 'Master en entrepreneuriat - Alternance à la Société Générale',
    ecole: 'Ort Montreuil Daniel Mayer - 3IL',
    date: '2023 - 2025',
  },
  {
    titre: 'Master Manager des Solutions Digitales et Data (MSD2) - Alternance à la Société Générale',
    ecole: 'Ort Montreuil Daniel Mayer - 3IL',
    date: '2023 - 2025',
  },
  {
    titre: "Bachelor Conception des systèmes informatiques - Alternance chez Delph Fiduciaire",
    ecole: 'Ort Montreuil Daniel Mayer',
    date: '2022 - 2023',
  },
  {
    titre: "BTS Services Informatiques aux Organisations (SIO) Option SLAM",
    ecole: 'Ort Montreuil Daniel Mayer',
    date: '2020 - 2022',
  },
]

// 🎬 Animation au scroll
onMounted(async () => {
  await nextTick()
  const elements = document.querySelectorAll('.fade')
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible')
          observer.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.15 }
  )
  elements.forEach((el) => observer.observe(el))
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
