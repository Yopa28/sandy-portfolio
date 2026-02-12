<template>
  <section class="py-20 px-6 max-w-[1200px] mx-auto">
    <div class="space-y-12">
      <div class="flex items-center gap-4">
        <h2 class="text-2xl font-black uppercase tracking-widest">Experience</h2>
        <div class="h-px bg-gray-200 dark:bg-white/10 flex-1"></div>
      </div>

      <div class="relative space-y-8 before:absolute before:inset-0 before:ml-5 before:-translate-x-px md:before:mx-auto md:before:translate-x-0 before:h-full before:w-0.5 before:bg-gradient-to-b before:from-transparent before:via-gray-200 dark:before:via-white/10 before:to-transparent">
        <div v-for="(item, index) in experience" :key="index" 
             class="relative flex items-center justify-between md:justify-normal md:odd:flex-row">
          <!-- Icon Circle -->
          <div class="flex items-center justify-center w-10 h-10 rounded-full border border-gray-100 dark:border-white/10 bg-white dark:bg-gray-800 text-primary shadow shrink-0 md:order-1 md:group-odd:-translate-x-1/2 md:group-even:translate-x-1/2 transition-all duration-300 group-hover:bg-primary group-hover:text-white group-hover:scale-110">
            <span class="material-symbols-outlined text-[20px]">{{ item.icon }}</span>
          </div>

          <!-- Content Card -->
          <div class="w-[calc(100%-4rem)] md:w-[45%] p-6 rounded-2xl bg-white dark:bg-white/5 border border-gray-100 dark:border-white/5 hover:border-primary/20 transition-all duration-300">
            <div class="flex items-center justify-between gap-4 mb-2">
              <span class="text-xs font-black text-primary uppercase tracking-widest">{{ item.date }}</span>
            </div>
            <h3 class="text-xl font-bold mb-1">{{ item.role }}</h3>
            <p class="text-sm font-bold opacity-70 mb-3">{{ item.company }}</p>
            <p class="text-sm text-[#637588] dark:text-gray-400 leading-relaxed">{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const experience = [
  {
    date: '2025',
    role: 'Web Application Developer (Intern)',
    company: 'Dinas Komunikasi dan Informatika Dairi',
    description: 'Leading the development of modern web applications using PHP and Flutter for civic infrastructure improvement.',
    icon: 'work'
  },
]
</script>