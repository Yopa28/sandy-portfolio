<script setup>
defineProps({
  title: String,
  tech: String,
  img: String,
  src: String,
  category: String,
  aspectRatio: {
    type: String,
    default: 'video'
  }
})
</script>

<template>
  <div class="group relative flex flex-col bg-white dark:bg-gray-800/50 border border-gray-100 dark:border-white/5 rounded-[2rem] overflow-hidden hover:shadow-2xl hover:shadow-primary/10 transition-all duration-500 hover:-translate-y-2">
    <!-- Image Container -->
    <div 
      :class="[
        'relative overflow-hidden m-3 rounded-[1.5rem] bg-gray-50 dark:bg-gray-900',
        aspectRatio === 'mobile' ? 'aspect-[4/5]' : 'aspect-[16/10]'
      ]"
    >
      <div 
        class="w-full h-full bg-cover transition-transform duration-700 group-hover:scale-110"
        :class="aspectRatio === 'mobile' ? 'bg-top' : 'bg-center'"
        :style="{ backgroundImage: `url(${img || src})` }"
      ></div>
      
      <!-- Category Tag -->
      <div class="absolute top-4 left-4">
        <span class="px-3 py-1 bg-white/90 dark:bg-gray-900/90 backdrop-blur-md rounded-full text-[10px] font-black uppercase tracking-widest shadow-sm">
          {{ category }}
        </span>
      </div>

      <div class="absolute inset-0 bg-gradient-to-t from-[#111418]/80 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500 flex items-end p-6">
        <span class="text-white text-sm font-bold flex items-center gap-2">
          View Project <span class="material-symbols-outlined text-sm">open_in_new</span>
        </span>
      </div>
    </div>

    <!-- Content -->
    <div class="px-8 pb-8 pt-2 flex flex-col">
      <h3 class="text-xl font-bold mb-2 group-hover:text-primary transition-colors">{{ title }}</h3>
      <p class="text-sm text-[#637588] dark:text-gray-400 font-medium leading-relaxed">{{ tech }}</p>
      
      <!-- Footer Area (Slot) -->
      <div v-if="$slots.footer" class="mt-6 pt-4 border-t border-gray-100 dark:border-white/5 flex gap-4">
        <slot name="footer"></slot>
      </div>
    </div>
  </div>
</template>