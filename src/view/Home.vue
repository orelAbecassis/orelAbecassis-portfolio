<template>
  <div class="w-full overflow-x-hidden">
    <HeroSection />
    <AboutSection />
    <ProjectsSection />
    <ContactSection /> 
    <FooterSection />
  </div>
</template>

<script setup lang="ts">
import HeroSection from '../components/HeroSection.vue'
import ProjectsSection from '../components/ProjectsSection.vue'
import AboutSection from '../components/AboutSection.vue'
import ContactSection from '../components/ContactSection.vue'
import FooterSection from '../components/FooterSection.vue'
</script>
