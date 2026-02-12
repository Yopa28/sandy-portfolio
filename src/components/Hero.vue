<script setup>
defineEmits(['navigate'])
</script>

<template>
  <section class="relative min-h-[90vh] flex flex-col items-center justify-center overflow-hidden pt-16 pb-24 px-6">
    <!-- Background Accents -->
    <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full max-w-[1200px] h-full pointer-events-none -z-10">
      <div class="absolute top-[-10%] right-[-10%] w-[500px] h-[500px] bg-primary/20 rounded-full blur-[120px] animate-pulse"></div>
      <div class="absolute bottom-[10%] left-[-10%] w-[400px] h-[400px] bg-blue-400/20 rounded-full blur-[100px] animate-pulse"></div>
    </div>

    <div class="max-w-[1200px] mx-auto flex flex-col items-center text-center">
      <!-- Profile Photo with Animated Glow -->
      <div class="relative mb-12 group reveal">
        <div class="absolute -inset-4 bg-gradient-to-r from-primary via-blue-400 to-primary rounded-full blur-xl opacity-20 group-hover:opacity-40 animate-spin-slow transition duration-1000"></div>
        <div class="relative h-44 w-44 rounded-full border-4 border-white dark:border-gray-800 shadow-2xl overflow-hidden bg-white ring-8 ring-gray-50/50 dark:ring-white/5">
          <img alt="Sandy Yopa" 
               class="h-full w-full object-cover object-top scale-100 group-hover:scale-110 transition-transform duration-700" 
               src="/images/sandyyy.jpg">
        </div>
      </div>

      <div class="space-y-6 max-w-4xl">
        <div class="reveal" style="transition-delay: 100ms">
          <p class="text-sm md:text-base text-primary font-black uppercase tracking-[0.3em] mb-4">
            Hello, I am
          </p>
          <h1 class="text-5xl md:text-7xl font-black tracking-tight leading-tight text-[#111418] dark:text-white">
            Sandy Yopa <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-blue-400">Boangmanalu</span>
          </h1>
        </div>

        <div class="reveal" style="transition-delay: 200ms">
          <p class="text-xl md:text-2xl text-[#637588] dark:text-gray-400 font-medium leading-relaxed max-w-2xl mx-auto">
            Junior Fullstack Developer | Machine Learning 
          </p>
        </div>
      </div>

      <div class="flex flex-wrap justify-center gap-6 mt-12 reveal" style="transition-delay: 300ms">
        <button 
          @click="$emit('navigate', 'project')"
          class="group relative bg-primary hover:bg-primary/90 text-white px-10 py-4 rounded-2xl font-black transition-all shadow-xl shadow-primary/25 active:scale-95 overflow-hidden">
          <span class="relative z-10 flex items-center gap-2">
            View My Works <span class="material-symbols-outlined text-[20px] group-hover:translate-x-1 transition-transform">arrow_forward</span>
          </span>
        </button>
        <button 
          @click="$emit('navigate', 'contact')"
          class="bg-white dark:bg-white/5 border-2 border-gray-100 dark:border-white/10 px-10 py-4 rounded-2xl font-black hover:bg-gray-50 dark:hover:bg-white/10 transition-all active:scale-95 text-[#111418] dark:text-white">
          Let's Talk
        </button>
      </div>
    </div>


    <!-- Scroll Down Indicator -->
    <div class="absolute bottom-8 center-1/2 -translate-x-1/2 flex flex-col items-center gap-2 animate-bounce opacity-40">
      <span class="text-[10px] font-black uppercase tracking-[0.2em]">Scroll Down</span>
      <span class="material-symbols-outlined">expand_more</span>
    </div>
  </section>
</template>