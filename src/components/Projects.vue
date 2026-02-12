<template>
  <section class="py-20 px-6 max-w-[1200px] mx-auto overflow-hidden">
    <!-- Section Header -->
    <div class="flex items-center gap-4 mb-12">
      <h2 class="text-2xl font-black uppercase tracking-widest shrin-0">
        {{ title || 'Featured Projects' }}
      </h2>
      <div class="h-px bg-gray-200 dark:bg-white/10 flex-1"></div>
      <a v-if="showSeeAll" href="#" 
         @click.prevent="$emit('navigate', 'project')"
         class="hidden md:flex items-center gap-2 text-primary text-sm font-black uppercase tracking-wider hover:gap-3 transition-all">
        See All <span class="material-symbols-outlined text-[18px]">arrow_forward</span>
      </a>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 md:gap-10 items-start">
      <ProjectCard 
        title="Cashwave App"
        category="Mobile App"
        tech="Flutter • Dart • Figma"
        src="/images/CashWave.jpg" 
        alt="Cashwave App"
        aspectRatio="mobile"
      />

      <ProjectCard 
        title="Cashwave Dashboard"
        category="Web Dashboard"
        tech="JavaScript • HTML • CSS"
        src="/images/dashboard.png"
        alt="Cashwave Dashboard"
        aspectRatio="desktop"
      />
      <ProjectCard 
        title="Kedai Sepijak"
        category="Fullstack Web"
        tech="Vue.js • Javascript • Express.js"
        src="/images/sepijak.png"
        alt="Kedai Sepijak"
        aspectRatio="desktop"
      />
    </div>

    <!-- Mobile See All -->
    <div v-if="showSeeAll" class="mt-12 flex md:hidden justify-center font-black">
       <a href="#" 
          @click.prevent="$emit('navigate', 'project')"
          class="flex items-center gap-2 text-primary text-sm uppercase tracking-wider">
        See All Projects <span class="material-symbols-outlined text-[18px]">arrow_forward</span>
      </a>
    </div>
  </section>
</template>

<script setup>
import { defineAsyncComponent } from 'vue'
const ProjectCard = defineAsyncComponent(() => import('./ProjectCard.vue'))

defineProps({
  title: String,
  showSeeAll: {
    type: Boolean,
    default: true
  }
})

defineEmits(['navigate'])
</script>