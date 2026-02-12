<script setup>
import { ref } from 'vue'

const props = defineProps({
  isDark: Boolean,
  currentPage: String
})

const emit = defineEmits(['toggle-dark', 'navigate'])
const isMenuOpen = ref(false)

const handleNavigate = (page) => {
  emit('navigate', page)
  isMenuOpen.value = false
}
</script>

<template>
  <header class="sticky top-0 z-50 w-full border-b border-solid border-[#f0f2f4] dark:border-[#2d3748] bg-white/80 dark:bg-background-dark/80 backdrop-blur-md">
    <div class="mx-auto max-w-[1200px] px-6 py-4 flex items-center justify-between">
      <!-- Logo -->
      <div class="flex items-center gap-4 text-primary cursor-pointer group" @click="handleNavigate('home')">
        <div class="size-8 group-hover:rotate-12 transition-transform duration-300">
          <svg fill="currentColor" viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
            <path d="M44 11.2727C44 14.0109 .8386 16.3957 33.69 17.6364C39.8386 18. 21.2618 44 24 44C12.9543 44 4 40.7439 4 36.7273C4 33.9891 8.16144 31.6043 14.31 30.3636C8.16144 29.123 4 26.7382 4 24C4 21.2618 8.16144 18.877 14.31 17.6364C8.16144 16.3957 4 14.0109 4 11.2727C4 7.25611 12.9543 4 24 4C35.0453 4 44 7.25611 44 11.2727Z"></path>
          </svg>
        </div>
        <h2 class="text-xl font-black tracking-tight">Sandy Yopa</h2>
      </div>

      <!-- Desktop Nav -->
      <nav class="hidden md:flex items-center gap-1">
        <template v-for="page in ['home', 'project', 'about', 'contact']" :key="page">
          <a 
            href="#" 
            @click.prevent="handleNavigate(page)" 
            :class="[
              'relative px-5 py-2 text-sm font-bold capitalize transition-all duration-300',
              currentPage === page ? 'text-primary' : 'text-[#637588] dark:text-gray-400 hover:text-primary'
            ]"
          >
            {{ page }}
            <!-- Active Indicator Line -->
            <div 
              v-if="currentPage === page" 
              class="absolute bottom-0 left-1/2 -translate-x-1/2 w-4 h-1 bg-primary rounded-full"
            ></div>
          </a>
        </template>
      </nav>

      <div class="flex items-center gap-4">
        <!-- Dark Mode Toggle -->
        <button
          @click="$emit('toggle-dark')"
          class="p-2.5 rounded-xl hover:bg-gray-100 dark:hover:bg-white/5 transition-all active:scale-90"
          aria-label="Toggle dark mode"
        >
          <span v-if="!isDark" class="material-symbols-outlined !text-[20px]">dark_mode</span>
          <span v-else class="material-symbols-outlined !text-[20px]">light_mode</span>
        </button>

        <!-- Mobile Menu Toggle -->
        <button
          @click="isMenuOpen = !isMenuOpen"
          class="md:hidden p-2.5 rounded-xl hover:bg-gray-100 dark:hover:bg-white/5 transition-all"
        >
          <span class="material-symbols-outlined !text-[24px]">
            {{ isMenuOpen ? 'close' : 'menu' }}
          </span>
        </button>
      </div>
    </div>

    <!-- Mobile Navigation Overlay -->
    <transition
      enter-active-class="transition duration-300 ease-out"
      enter-from-class="opacity-0 -translate-y-4"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition duration-200 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-4"
    >
      <div v-if="isMenuOpen" class="md:hidden absolute top-full left-0 w-full bg-white dark:bg-background-dark border-b border-gray-100 dark:border-white/5 shadow-2xl">
        <nav class="flex flex-col p-6 gap-2">
          <a 
            v-for="page in ['home', 'project', 'about', 'contact']" 
            :key="page"
            href="#" 
            @click.prevent="handleNavigate(page)"
            :class="[
              'flex items-center justify-between p-4 rounded-2xl text-lg font-bold capitalize transition-all',
              currentPage === page ? 'bg-primary/10 text-primary' : 'hover:bg-gray-50 dark:hover:bg-white/5'
            ]"
          >
            {{ page }}
            <span v-if="currentPage === page" class="material-symbols-outlined text-[18px]">chevron_right</span>
          </a>
        </nav>
      </div>
    </transition>
  </header>
</template>