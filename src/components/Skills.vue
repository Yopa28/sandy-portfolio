<template>
  <section class="py-20 px-6 max-w-[1200px] mx-auto overflow-hidden">
    <div class="space-y-16">
      <div class="flex items-center gap-4">
        <h2 class="text-2xl font-black uppercase tracking-widest">My Skills</h2>
        <div class="h-px bg-gray-200 dark:bg-white/10 flex-1"></div>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-12">
        <div v-for="(group, gIndex) in skillGroups" :key="group.category" 
             class="space-y-6 reveal" :style="{ transitionDelay: `${gIndex * 150}ms` }">
          <h3 class="text-sm font-black text-primary uppercase tracking-[0.2em] opacity-80">{{ group.category }}</h3>
          <div class="flex flex-col gap-3">
            <div v-for="skill in group.skills" :key="skill.name" 
                 class="group flex items-center gap-4 p-4 bg-white dark:bg-white/5 border border-gray-100 dark:border-white/5 rounded-2xl hover:border-primary/30 hover:shadow-xl hover:shadow-primary/5 transition-all duration-300">
              <div :class="`p-2.5 rounded-xl ${skill.color} bg-opacity-10 transition-all duration-500 group-hover:bg-primary group-hover:bg-opacity-100 group-hover:text-white group-hover:scale-110 shadow-sm text-[20px] flex items-center justify-center`">
                <span class="material-symbols-outlined">{{ skill.icon }}</span>
              </div>
              <p class="font-bold text-base text-[#111418] dark:text-gray-200">{{ skill.name }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skillGroups = [
  {
    category: 'Core Engineering',
    skills: [
      { name: 'Python', icon: 'terminal', color: 'text-green-500' },
      { name: 'C++', icon: 'code', color: 'text-indigo-500' },
      { name: 'JavaScript', icon: 'javascript', color: 'text-yellow-500' }
    ]
  },
  {
    category: 'Web & Mobile',
    skills: [
      { name: 'Flutter', icon: 'flutter', color: 'text-blue-400' },
      { name: 'PHP', icon: 'php', color: 'text-blue-500' },
      { name: 'Vue.js', icon: 'data_object', color: 'text-emerald-500' }
    ]
  },
  {
    category: 'Tools & Database',
    skills: [
      { name: 'MySQL', icon: 'database', color: 'text-cyan-600' },
      { name: 'Figma', icon: 'palette', color: 'text-pink-500' }
    ]
  }
]
</script>