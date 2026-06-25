<script setup>
import { Icon } from '@iconify/vue'

const skillGroups = [
  {
    category: 'Backend',
    skills: [
      { name: 'Golang', icon: 'skill-icons:golang' },
      { name: 'Laravel', icon: 'skill-icons:laravel-dark' },
      { name: 'Node.js', icon: 'skill-icons:nodejs-dark' },
      { name: 'Express.js', icon: 'skill-icons:expressjs-dark' }
    ]
  },
  {
    category: 'Frontend & Mobile',
    skills: [
      { name: 'Vue.js', icon: 'skill-icons:vuejs-dark' },
      { name: 'Flutter', icon: 'skill-icons:flutter-dark' },
      { name: 'JavaScript', icon: 'skill-icons:javascript' }
    ]
  },
  {
    category: 'Database & Tools',
    skills: [
      { name: 'MySQL', icon: 'skill-icons:mysql-dark' },
      { name: 'Git', icon: 'skill-icons:git' },
      { name: 'Docker', icon: 'skill-icons:docker' },
      { name: 'Postman', icon: 'skill-icons:postman' },
      { name: 'Figma', icon: 'skill-icons:figma-dark' }
    ]
  }
]
</script>

<template>
  <section class="py-20 px-6 max-w-[1200px] mx-auto overflow-hidden">
    <div class="space-y-16">
      <div class="flex items-center gap-4">
        <h2 class="text-2xl font-black uppercase tracking-widest">
          My Skills
        </h2>
        <div class="h-px bg-gray-200 dark:bg-white/10 flex-1"></div>
      </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-8 md:gap-12">
    <div
      v-for="(group, gIndex) in skillGroups"
      :key="group.category"
      class="space-y-6 reveal"
      :style="{ transitionDelay: `${gIndex * 150}ms` }"
    >
      <h3 class="text-sm font-black text-primary uppercase tracking-[0.2em] opacity-80">
        {{ group.category }}
      </h3>

      <div class="flex flex-col gap-3">
        <div
          v-for="skill in group.skills"
          :key="skill.name"
          class="group flex items-center gap-3 sm:gap-4 p-3 sm:p-4 bg-white dark:bg-white/5 border border-gray-100 dark:border-white/5 rounded-2xl hover:border-primary/30 hover:shadow-xl hover:shadow-primary/5 transition-all duration-300"
        >
          <div
            class="p-2.5 rounded-xl bg-primary/5 flex items-center justify-center transition-all duration-300 group-hover:scale-110"
          >
            <Icon :icon="skill.icon" class="text-[30px]" />
          </div>

          <p class="font-bold text-base text-[#111418] dark:text-gray-200">
            {{ skill.name }}
          </p>
        </div>
      </div>
    </div>
  </div>
</div>

  </section>
</template>
