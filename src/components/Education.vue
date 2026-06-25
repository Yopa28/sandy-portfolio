<template>
  <section class="py-20 px-6 max-w-[1200px] mx-auto">
    <div class="space-y-12">
      <div class="flex items-center gap-4">
        <h2 class="text-2xl font-black uppercase tracking-widest">Education</h2>
        <div class="h-px bg-gray-200 dark:bg-white/10 flex-1"></div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div v-for="edu in education" :key="edu.school" 
             class="group p-6 sm:p-8 rounded-[2rem] bg-white dark:bg-white/5 border border-gray-100 dark:border-white/5 hover:border-primary/20 transition-all duration-300 hover:shadow-xl hover:shadow-primary/5">
          <div class="flex flex-col h-full">
            <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 mb-6">
              <div class="p-3 bg-primary/10 rounded-2xl text-primary w-fit">
                <span class="material-symbols-outlined text-[28px]">school</span>
              </div>
              <span class="text-xs font-black text-primary uppercase tracking-widest bg-primary/5 px-4 py-1.5 rounded-full self-start sm:self-auto">{{ edu.date }}</span>
            </div>
            <h3 class="text-2xl font-bold mb-2 group-hover:text-primary transition-colors">{{ edu.degree }}</h3>
            <p class="text-lg font-bold opacity-70 mb-4">{{ edu.school }}</p>
            <div v-if="edu.gpa" class="mt-auto">
              <span class="px-3 py-1 bg-green-500/10 text-green-600 dark:text-green-400 rounded-lg text-sm font-bold border border-green-500/10">GPA {{ edu.gpa }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const education = [
  {
    degree: 'Informatics Engineering',
    school: 'Telkom University Purwokerto',
    date: '2022 - 2026',
    gpa: '3.75 / 4.00'
  },
  {
    degree: 'Science (MIPA)',
    school: 'SMA Negeri 1 Sidikalang',
    date: '2019 - 2022'
  }
]
</script>