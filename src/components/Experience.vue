<script setup>
const cvUrl = "/Sandy_CV.pdf"

const experiences = [
  {
    id: 1,
    company: 'Kedai Sepijak',
    position: 'Fullstack Developer',
    type: 'Contract',
    location: 'Purwokerto, Indonesia',
    period: 'Sept 2025 – Jan 2026',
    achievements: [
      'Developed and maintained a full-stack cafe management website using Vue 3, Express.js, and MySQL.',
      'Built RESTful APIs using Express.js.',
      'Developed menu display, voting system, and customer feedback features.',
      'Performed frontend optimization, regression testing, and troubleshooting.',
      'Created project documentation and collaborated using Git & GitHub.'
    ],
    technologies: ['Vue 3', 'JavaScript', 'Express.js', 'MySQL', 'Git', 'GitHub']
  },
  {
    id: 2,
    company: 'Dinas Komunikasi dan Informatika',
    position: 'Fullstack Developer Intern',
    type: 'Internship',
    location: 'Dairi, Indonesia',
    period: 'Jul 2025 – Aug 2025',
    achievements: [
      'Built and maintained a Point of Sale system using Laravel.',
      'Designed backend logic and managed MySQL databases.',
      'Developed a Flutter mobile application.',
      'Assisted software configuration, testing, and deployment.',
      'Created technical documentation and user guides.'
    ],
    technologies: ['Laravel', 'PHP', 'Flutter', 'MySQL', 'Git']
  }
]
</script>


<template>
  <section class="py-20 px-6 max-w-[1200px] mx-auto overflow-hidden" id="experience">
    <!-- Section Header -->
    <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-6 mb-16">
      <div class="flex items-center gap-4 flex-1 w-full">
        <h2 class="text-2xl font-black uppercase tracking-widest shrink-0">
          Experience
        </h2>
        <div class="h-px bg-gray-200 dark:bg-white/10 flex-1"></div>
      </div>
<a
  href="/Sandy_CV.pdf"
  download="Sandy_CV.pdf"
  class="inline-flex items-center justify-center gap-2 px-6 py-3 bg-primary text-white rounded-xl font-bold hover:shadow-xl hover:shadow-primary/20 transition-all"
>
  <span class="material-symbols-outlined text-[20px]">
    download
  </span>
  Download CV
</a>
    </div>

    <!-- Timeline Container -->
    <div class="relative ml-2 sm:ml-0 pl-6 md:pl-8 space-y-12 before:absolute before:inset-0 before:ml-6 md:before:ml-8 before:-translate-x-px md:before:-translate-x-0.5 before:h-full before:w-0.5 before:bg-gradient-to-b before:from-primary/50 before:via-primary/20 before:to-transparent">
      
      <div 
        v-for="(exp, index) in experiences" 
        :key="exp.id"
        class="relative group reveal"
        :style="{ transitionDelay: `${index * 150}ms` }"
      >
        <!-- Timeline Dot -->
        <div class="absolute -left-[29px] md:-left-[35px] top-4 md:top-6 h-3 w-3 md:h-4 md:w-4 rounded-full bg-primary ring-4 ring-white dark:ring-[#111418] group-hover:scale-150 group-hover:shadow-[0_0_15px_rgba(var(--color-primary),0.5)] transition-all duration-300 z-10"></div>

        <!-- Experience Card -->
        <div class="bg-white dark:bg-white/5 border border-gray-100 dark:border-white/5 rounded-2xl p-6 md:p-8 hover:border-primary/30 hover:shadow-xl hover:shadow-primary/5 transition-all duration-500 transform group-hover:-translate-y-1">
          
          <!-- Header (Position & Period) -->
          <div class="flex flex-col md:flex-row md:items-start justify-between gap-4 mb-4">
            <div>
              <h3 class="text-xl md:text-2xl font-black text-[#111418] dark:text-white mb-1 group-hover:text-primary transition-colors">
                {{ exp.position }}
              </h3>
              <div class="flex flex-wrap items-center gap-2 text-sm md:text-base font-medium text-gray-600 dark:text-gray-400">
                <span class="text-primary">{{ exp.company }}</span>
                <span class="w-1.5 h-1.5 rounded-full bg-gray-300 dark:bg-gray-600 hidden md:block"></span>
                <span>{{ exp.type }}</span>
                <span class="w-1.5 h-1.5 rounded-full bg-gray-300 dark:bg-gray-600 hidden md:block"></span>
                <span>{{ exp.location }}</span>
              </div>
            </div>
            <div class="inline-flex items-center px-4 py-2 rounded-full bg-primary/10 text-primary text-sm font-bold whitespace-nowrap self-start md:self-auto">
              {{ exp.period }}
            </div>
          </div>

          <!-- Achievements -->
          <ul class="space-y-3 mb-6 text-gray-600 dark:text-gray-300">
            <li 
              v-for="(achievement, i) in exp.achievements" 
              :key="i"
              class="flex items-start gap-3 text-sm md:text-base"
            >
              <span class="material-symbols-outlined text-primary text-[20px] shrink-0 mt-0.5">check_circle</span>
              <span class="leading-relaxed">{{ achievement }}</span>
            </li>
          </ul>

          <!-- Technologies -->
          <div class="flex flex-wrap gap-2 pt-6 border-t border-gray-100 dark:border-white/10">
            <span 
              v-for="tech in exp.technologies" 
              :key="tech"
              class="px-3 py-1 text-xs md:text-sm font-semibold rounded-lg bg-gray-100 dark:bg-white/10 text-gray-700 dark:text-gray-300 hover:bg-primary hover:text-white dark:hover:bg-primary transition-colors cursor-default"
            >
              {{ tech }}
            </span>
          </div>

        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
/* Icon Material Symbols Outlined is assumed to be globally available like in other components. If not, it falls back gracefully or should be imported if required. It looks like Projects.vue uses it directly. */
.reveal {
  opacity: 0;
  animation: fadeUp 0.8s ease-out forwards;
}

@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
