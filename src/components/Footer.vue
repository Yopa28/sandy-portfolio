<template>
  <footer class="mt-20 border-t border-[#f0f2f4] dark:border-white/10 bg-white dark:bg-background-dark pt-16 pb-8">
    <div class="mx-auto max-w-[1200px] px-6">
      <div class="flex flex-col md:flex-row justify-between items-start gap-12 mb-16">
        <div class="space-y-4 max-w-sm">
          <div class="flex items-center gap-3 text-primary">
            <div class="size-8">
              <svg fill="currentColor" viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
                <path d="M44 11.2727C44 14.0109 .8386 16.3957 33.69 17.6364C39.8386 18. 21.2618 44 24 44C12.9543 44 4 40.7439 4 36.7273C4 33.9891 8.16144 31.6043 14.31 30.3636C8.16144 29.123 4 26.7382 4 24C4 21.2618 8.16144 18.877 14.31 17.6364C8.16144 16.3957 4 14.0109 4 11.2727C4 7.25611 12.9543 4 24 4C35.0453 4 44 7.25611 44 11.2727Z"></path>
              </svg>
            </div>
            <h2 class="text-xl font-black tracking-tight text-[#111418] dark:text-white">Sandy Yopa</h2>
          </div>
          <p class="text-sm text-[#637588] dark:text-gray-400 leading-relaxed">
          Informatics Engineering Graduate | Fullstack Developer
          </p>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 gap-10 sm:gap-16 mt-12 md:mt-0">
          <div class="space-y-4">
            <h4 class="text-sm font-black uppercase tracking-widest">Navigation</h4>
            <div class="flex flex-col gap-2">
              <a @click.prevent="$emit('navigate', 'home')" href="#" class="text-sm text-[#637588] dark:text-gray-400 hover:text-primary transition-colors">Home</a>
              <a @click.prevent="$emit('navigate', 'project')" href="#" class="text-sm text-[#637588] dark:text-gray-400 hover:text-primary transition-colors">Projects</a>
              <a @click.prevent="$emit('navigate', 'experience')" href="#" class="text-sm text-[#637588] dark:text-gray-400 hover:text-primary transition-colors">Experience</a>
            </div>
          </div>
          <div class="space-y-4">
            <h4 class="text-sm font-black uppercase tracking-widest">Connect</h4>
            <div class="flex flex-col gap-2">
              <a href="https://www.linkedin.com/in/sandyyopa/" target="_blank" class="text-sm text-[#637588] dark:text-gray-400 hover:text-primary transition-colors">LinkedIn</a>
              <a href="https://github.com/Yopa28" target="_blank" class="text-sm text-[#637588] dark:text-gray-400 hover:text-primary transition-colors">GitHub</a>
              <a href="https://www.instagram.com/sandyyopa/" target="_blank" class="text-sm text-[#637588] dark:text-gray-400 hover:text-primary transition-colors">Instagram</a>
            </div>
          </div>
        </div>
      </div>

      <div class="pt-8 border-t border-[#f0f2f4] dark:border-white/5 flex flex-col md:flex-row justify-between items-center gap-4">
        <div class="text-[#111418]/40 dark:text-white/40 text-[12px] font-medium">
          © 2026 Sandy Yopa Boangmanalu. Built with Vue.js & Tailwind.
        </div>
        <button 
          @click="scrollToTop"
          class="group flex items-center gap-2 text-xs font-black uppercase tracking-widest hover:text-primary transition-colors"
        >
          Back to Top
          <span class="material-symbols-outlined text-sm group-hover:-translate-y-1 transition-transform">arrow_upward</span>
        </button>
      </div>
    </div>
  </footer>
</template>

<script setup>
defineEmits(['navigate'])

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>