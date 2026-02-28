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
const currentPage = ref('home') // 'home', 'project', 'about', 'contact'

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
  <div class="min-h-screen flex flex-col">
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
      
      <section v-else-if="currentPage === 'about'" class="reveal py-16 px-6 max-w-[1000px] mx-auto">
        <div class="space-y-20">
          <!-- Introduction Header -->
          <div class="flex flex-col items-center text-center space-y-6">
            <div class="relative group">
              <div class="absolute -inset-1 bg-gradient-to-r from-primary to-blue-400 rounded-2xl blur opacity-25 group-hover:opacity-40 transition duration-1000 group-hover:duration-200"></div>
              <div class="relative bg-white dark:bg-gray-800 rounded-2xl p-2 overflow-hidden border border-gray-100 dark:border-white/5 shadow-2xl">
                <img class="w-40 h-40 object-cover object-top rounded-xl"                
                     src="/images/sandyyy.jpg" 
                     alt="Sandy Yopa Boangmanalu">
              </div>
            </div>
            
            <div class="space-y-3">
              <h1 class="text-4xl md:text-5xl font-black tracking-tight">Sandy Yopa Boangmanalu</h1>
              <p class="text-primary text-lg font-bold uppercase tracking-[0.2em] opacity-90">Informatics Engineer</p>
            </div>

            <p class="max-w-3xl text-lg md:text-xl text-[#637588] dark:text-gray-400 leading-relaxed font-medium">
              I am a fresh graduate in Informatics Engineering from Telkom University Purwokerto, with a strong interest in <span class="text-[#111418] dark:text-white underline decoration-primary/30 decoration-4">Junior Full Stack Developer</span> 
              and exploring <span class="text-[#111418] dark:text-white underline decoration-primary/30 decoration-4">machine learning</span> solutions.
            </p>

            <div class="flex gap-4 pt-4">
              <a href="/CV_Sandy.pdf" download="CV_Sandy.pdf" class="flex items-center gap-2 px-8 py-4 bg-primary text-white rounded-2xl font-bold hover:shadow-xl hover:shadow-primary/20 transition-all active:scale-95">
                <span class="material-symbols-outlined">download</span> Download Resume
              </a>
            </div>
          </div>

          <!-- Journey Section -->
          <div class="space-y-12 pb-12">
            <div class="flex items-center gap-4">
              <h2 class="text-2xl font-black">Experience & Milestones</h2>
              <div class="h-px bg-gray-200 dark:bg-white/10 flex-1"></div>
            </div>

            <div class="grid gap-8">
              <!-- Item 1: Internship -->
              <div class="relative group p-8 rounded-3xl bg-white dark:bg-white/5 border border-gray-100 dark:border-white/5 hover:border-primary/20 transition-all duration-300">
                <div class="flex flex-col md:flex-row md:items-start justify-between gap-4">
                  <div class="space-y-3">
                    <div class="flex items-center gap-3">
                      <div class="p-2 bg-primary/10 rounded-lg text-primary">
                        <span class="material-symbols-outlined">work</span>
                      </div>
                      <span class="text-sm font-black text-primary uppercase tracking-widest">2025 • Internship</span>
                    </div>
                    <h3 class="text-2xl font-bold">Web Application Developer</h3>
                    <p class="text-lg font-bold opacity-70">Dinas Komunikasi dan Informatika Dairi</p>
                    <p class="text-[#637588] dark:text-gray-400 leading-relaxed max-w-2xl">
                      Focusing on PHP and Flutter development to improve provincial digital infrastructure and community-facing services.
                    </p>
                  </div>
                </div>
              </div>

              <!-- Item 2: Esports -->
              <div class="relative group p-8 rounded-3xl bg-white dark:bg-white/5 border border-gray-100 dark:border-white/5 hover:border-primary/20 transition-all duration-300">
                <div class="flex flex-col md:flex-row md:items-start justify-between gap-4">
                  <div class="space-y-3">
                    <div class="flex items-center gap-3">
                      <div class="p-2 bg-primary/10 rounded-lg text-primary">
                        <span class="material-symbols-outlined">military_tech</span>
                      </div>
                      <span class="text-sm font-black text-primary uppercase tracking-widest">2023 • Achievement</span>
                    </div>
                    <h3 class="text-2xl font-bold">PMCC 2nd Place Winner</h3>
                    <p class="text-lg font-bold opacity-70">Telkom University Esports</p>
                    <p class="text-[#637588] dark:text-gray-400 leading-relaxed max-w-2xl">
                      Competing at a professional level in PUBG Mobile Campus Championship. This journey honed my strategic thinking, leadership as a coordinator, and ability to thrive under high pressure.
                    </p>
                  </div>
                </div>
              </div>

              <!-- Item 3: University -->
              <div class="relative group p-8 rounded-3xl bg-white dark:bg-white/5 border border-gray-100 dark:border-white/5 hover:border-primary/20 transition-all duration-300">
                <div class="flex flex-col md:flex-row md:items-start justify-between gap-4">
                  <div class="space-y-3">
                    <div class="flex items-center gap-3">
                      <div class="p-2 bg-primary/10 rounded-lg text-primary">
                        <span class="material-symbols-outlined">school</span>
                      </div>
                      <span class="text-sm font-black text-primary uppercase tracking-widest">2022 — 2026</span>
                    </div>
                    <h3 class="text-2xl font-bold">Informatics Engineering</h3>
                    <p class="text-lg font-bold opacity-70">Telkom University Purwokerto</p>
                    <div class="flex flex-wrap gap-4 pt-2">
                       <span class="px-4 py-1.5 bg-green-500/10 text-green-600 dark:text-green-400 rounded-full text-sm font-bold border border-green-500/20">GPA 3.75 / 4.00</span>
                    </div>
                  </div>
                </div>
              </div>

              <!-- Item 4: High School -->
              <div class="relative group p-8 rounded-3xl bg-white dark:bg-white/5 border border-gray-100 dark:border-white/5 hover:border-primary/20 transition-all duration-300">
                <div class="flex flex-col md:flex-row md:items-start justify-between gap-4">
                  <div class="space-y-3">
                    <div class="flex items-center gap-3">
                      <div class="p-2 bg-primary/10 rounded-lg text-primary">
                        <span class="material-symbols-outlined">history_edu</span>
                      </div>
                      <span class="text-sm font-black text-primary uppercase tracking-widest">2019 — 2022</span>
                    </div>
                    <h3 class="text-2xl font-bold">SMA N 1 Sidikalang</h3>
                    <p class="text-lg font-bold opacity-70">Science (MIPA)</p>
                    <p class="text-[#637588] dark:text-gray-400 leading-relaxed max-w-2xl">
                      Foundation of my engineering logic. Active in Football and Karate, maintaining a balanced lifestyle between academics and sports.
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <Contact v-else-if="currentPage === 'contact'" class="reveal" />
    </main>

    <Footer />
  </div>
</template>