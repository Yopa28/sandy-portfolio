<script setup>
import { ref, onMounted } from 'vue'
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import Projects from './components/Projects.vue'
import Experience from './components/Experience.vue'
import Skills from './components/Skills.vue'
import Education from './components/Education.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

const isDarkMode = ref(false)
const currentPage = ref('home') // 'home', 'project', 'experience', 'contact'

// Load saved preference
onMounted(() => {
  const saved = localStorage.getItem('darkMode')
  if (saved === 'true') {
    isDarkMode.value = true
    document.documentElement.classList.add('dark')
  }

  // Intersection Observer for Scroll Reveal
  const observerOptions = {
    threshold: 0.1
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('active')
      }
    })
  }, observerOptions)

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el))
})

const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value
  document.documentElement.classList.toggle('dark')
  localStorage.setItem('darkMode', String(isDarkMode.value))
}

const navigateTo = (page) => {
  currentPage.value = page
  window.scrollTo({ top: 0, behavior: 'smooth' })
  // Re-observe after navigation
  setTimeout(() => {
    document.querySelectorAll('.reveal').forEach(el => {
      el.classList.remove('active')
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) entry.target.classList.add('active')
        })
      })
      observer.observe(el)
    })
  }, 100)
}
</script>

<template>
  <div class="min-h-screen flex flex-col w-full overflow-x-hidden">
    <Header 
      @toggle-dark="toggleDarkMode" 
      :is-dark="isDarkMode"
      @navigate="navigateTo"
      :current-page="currentPage"
    />

    <main class="flex-1">
      <template v-if="currentPage === 'home'">
        <Hero @navigate="navigateTo" />
        <Projects class="reveal" title="Featured Projects" @navigate="navigateTo" />
        <Experience class="reveal" />
        <Skills class="reveal" />
        <Education class="reveal" />
      </template>
      
      <Projects v-else-if="currentPage === 'project'" class="reveal" title="All Projects" :show-see-all="false" />
      
      <Experience v-else-if="currentPage === 'experience'" class="reveal" />

      <Contact v-else-if="currentPage === 'contact'" class="reveal" />
    </main>

    <Footer />
  </div>
</template>