<script setup>
defineProps({
  title: String,
  category: String,
  tech: String,
  src: String,
  alt: String,
  aspectRatio: {
    type: String,
    default: 'desktop'
  },
  url: {
    type: String,
    default: ''
  }
})
</script>

<template>
  <a
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    class="group block focus:outline-none focus:ring-2 focus:ring-primary focus:ring-offset-2 dark:focus:ring-offset-background-dark rounded-3xl"
    :aria-label="`View project: ${title}`"
  >
    <article
      class="overflow-hidden rounded-3xl border border-gray-100 dark:border-white/10 bg-white dark:bg-white/5 hover:border-primary/30 hover:shadow-2xl hover:shadow-primary/10 transition-all duration-500"
    >
      <!-- Image -->
      <div
        :class="[
          'overflow-hidden',
          aspectRatio === 'mobile'
            ? 'aspect-[9/16]'
            : 'aspect-[16/10]'
        ]"
      >
        <img
          :src="src"
          :alt="alt"
          loading="lazy"
          decoding="async"
          class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
        />
      </div>

      <!-- Content -->
      <div class="p-6">
        <div class="flex items-start justify-between gap-4">
          <div>
            <p class="text-xs uppercase tracking-[0.2em] font-black text-primary">
              {{ category }}
            </p>

            <h3 class="mt-2 text-xl font-black text-[#111418] dark:text-white">
              {{ title }}
            </h3>

            <p class="mt-3 text-sm text-[#637588] dark:text-gray-400">
              {{ tech }}
            </p>
          </div>

          <span
            class="material-symbols-outlined text-primary opacity-70 transition-all duration-300 group-hover:translate-x-1 group-hover:-translate-y-1"
          >
            open_in_new
          </span>
        </div>
      </div>
    </article>
  </a>
</template>