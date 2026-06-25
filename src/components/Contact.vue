<template>
  <section class="py-12 px-6 max-w-[1200px] mx-auto">
    <div class="flex flex-col lg:flex-row gap-16">
      <!-- Left: Form -->
      <div class="flex-1 space-y-4">
        <h1 class="text-4xl font-black mb-2">Contact Me</h1>
        <p class="text-base text-[#637588] dark:text-gray-400 mb-8">Let's build something amazing together.</p>

        <div class="space-y-4">
          <div class="flex flex-wrap items-end gap-4 py-3">
            <label class="flex flex-col min-w-40 flex-1" for="contact-name">
              <span class="text-[#111418] dark:text-white text-base font-medium mb-2">Name</span>
              <input id="contact-name" class="form-input w-full min-w-0 flex-1 resize-none overflow-hidden rounded-lg text-[#111418] dark:text-white focus:outline-none focus:ring-2 focus:ring-primary border border-[#dce0e5] dark:border-gray-700 bg-white dark:bg-gray-800 h-14 placeholder:text-[#637588] p-[15px] text-base" placeholder="Enter your full name" type="text"/>
            </label>
          </div>
          <div class="flex flex-wrap items-end gap-4 py-3">
            <label class="flex flex-col min-w-40 flex-1" for="contact-email">
              <span class="text-[#111418] dark:text-white text-base font-medium mb-2">Email</span>
              <input id="contact-email" class="form-input w-full min-w-0 flex-1 resize-none overflow-hidden rounded-lg text-[#111418] dark:text-white focus:outline-none focus:ring-2 focus:ring-primary border border-[#dce0e5] dark:border-gray-700 bg-white dark:bg-gray-800 h-14 placeholder:text-[#637588] p-[15px] text-base" placeholder="email@example.com" type="email"/>
            </label>
          </div>
          <div class="flex flex-wrap items-end gap-4 py-3">
            <label class="flex flex-col min-w-40 flex-1" for="contact-subject">
              <span class="text-[#111418] dark:text-white text-base font-medium mb-2">Subject</span>
              <input id="contact-subject" class="form-input w-full min-w-0 flex-1 resize-none overflow-hidden rounded-lg text-[#111418] dark:text-white focus:outline-none focus:ring-2 focus:ring-primary border border-[#dce0e5] dark:border-gray-700 bg-white dark:bg-gray-800 h-14 placeholder:text-[#637588] p-[15px] text-base" placeholder="What's this about?" type="text"/>
            </label>
          </div>
          <div class="flex flex-wrap items-end gap-4 py-3">
            <label class="flex flex-col min-w-40 flex-1" for="contact-message">
              <span class="text-[#111418] dark:text-white text-base font-medium mb-2">Message</span>
              <textarea id="contact-message" class="form-input w-full min-w-0 flex-1 resize-none overflow-hidden rounded-lg text-[#111418] dark:text-white focus:outline-none focus:ring-2 focus:ring-primary border border-[#dce0e5] dark:border-gray-700 bg-white dark:bg-gray-800 placeholder:text-[#637588] p-[15px] text-base" placeholder="Tell me more about your project..." rows="5"></textarea>
            </label>
          </div>
          <div class="py-4">
            <button class="w-full flex min-w-[120px] items-center justify-center rounded-lg h-14 px-8 bg-primary text-white text-base font-bold hover:bg-primary/90 transition-all">
              Send Message
            </button>
          </div>
        </div>
      </div>

      <!-- Right: Info -->
      <div class="lg:w-1/3 flex flex-col gap-10">
        <div class="flex flex-col gap-6">
          <h3 class="text-xl font-bold">Contact Details</h3>
          <div class="flex items-start gap-4">
            <div class="flex size-10 items-center justify-center rounded-lg bg-primary/10 text-primary">
              <span class="material-symbols-outlined">mail</span>
            </div>
            <div>
              <p class="text-[#111418] dark:text-white font-medium">Email</p>
              <p class="text-[#637588] dark:text-gray-400">sandyboangmanalu@gmail.com</p>
            </div>
          </div>
          <div class="flex items-start gap-4">
            <div class="flex size-10 items-center justify-center rounded-lg bg-primary/10 text-primary">
              <span class="material-symbols-outlined">location_on</span>
            </div>
            <div>
              <p class="text-[#111418] dark:text-white font-medium">Location</p>
              <p class="text-[#637588] dark:text-gray-400">Purwokerto, Indonesia</p>
            </div>
          </div>
        </div>

        <div class="flex flex-col gap-6">
          <h3 class="text-xl font-bold">Follow Me</h3>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <a href="https://www.linkedin.com/in/sandyyopa/" target="_blank" class="flex items-center gap-3 p-4 rounded-xl border border-[#dce0e5] dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-800 transition-colors">
              <div class="text-[#111418] dark:text-white">
                <svg class="size-6" fill="currentColor" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"></path></svg>
              </div>
              <span class="font-medium dark:text-white">LinkedIn</span>
            </a>
            <a href="https://github.com/Yopa28" target="_blank" class="flex items-center gap-3 p-4 rounded-xl border border-[#dce0e5] dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-800 transition-colors">
              <div class="text-[#111418] dark:text-white">
                <svg class="size-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.43.372.823 1.102.823 2.222 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"></path></svg>
              </div>
              <span class="font-medium dark:text-white">GitHub</span>
            </a>
            <a href="https://www.instagram.com/sandyyopa/" target="_blank" class="flex items-center gap-3 p-4 rounded-xl border border-[#dce0e5] dark:border-gray-700 hover:bg-gray-50 dark:hover:bg-gray-800 transition-colors">
              <div class="text-[#111418] dark:text-white">
                <svg class="size-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"></path></svg>
              </div>
              <span class="font-medium dark:text-white">Instagram</span>
            </a>
          </div>
        </div>

        <div class="p-8 rounded-2xl bg-primary text-white flex flex-col gap-4">
          <h4 class="text-xl font-bold">Quick Chat?</h4>
          <p class="text-white/80 leading-relaxed">I'm usually available for projects and remote collaborations. Drop a message!</p>
          <a class="inline-flex items-center gap-2 font-bold hover:underline" href="mailto:sandyboangmanalu@gmail.com">
            Send an email
            <span class="material-symbols-outlined text-sm">arrow_forward</span>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>