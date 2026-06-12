<template>
  <NavBar />
  <HeroSection />
  <SkillsSection />
  <ProjectsSection />
  <ContactSection />
  <SiteFooter />
</template>

<script setup>
import { onMounted } from 'vue'
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import ContactSection from './components/ContactSection.vue'
import SiteFooter from './components/SiteFooter.vue'

onMounted(() => {
  const reveals = document.querySelectorAll('.reveal')
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry, i) => {
        if (entry.isIntersecting) {
          setTimeout(() => entry.target.classList.add('visible'), i * 80)
          observer.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.1 }
  )
  reveals.forEach((el) => observer.observe(el))
})
</script>

<style>
* { box-sizing: border-box; margin: 0; padding: 0; }
</style>
