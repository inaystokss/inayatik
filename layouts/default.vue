<template>
    <div class="flex flex-col min-h-screen">
      <!-- Header -->
      <header class="flex items-center justify-between bg-yellow-700 p-1 border-b-1 border-gray-400 relative"> 
        <!-- Логотип -->
        <div>
          <img src="/assets/images/cats.png" class="w-25 h-25" alt="Logo" />
        </div>
  
        <!-- Бургер -->
        <div class="cursor-pointer text-3xl z-20" @click="switchBurger">
          <span v-if="!burger">☰</span>
          <span v-else>✖</span>
        </div>
  
        <!-- Навигация -->
        <nav
          :class="[
            'flex-col absolute top-full left-0 w-full bg-white text-black text-center transition-all duration-300 z-10',
            burger ? 'flex' : 'hidden'
          ]"
        >
          <NuxtLink to="/" class="p-3 border-b hover:bg-gray-300">Home</NuxtLink>
          <NuxtLink to="/lab3" class="p-3 border-b hover:bg-gray-300">Lab3</NuxtLink>
          <NuxtLink to="/lab4" class="p-3 border-b hover:bg-gray-300">Lab4</NuxtLink>
          <NuxtLink to="/login" class="p-3 border-b hover:bg-gray-300">Login</NuxtLink>
          <NuxtLink to="/logout" class="p-3 hover:bg-gray-300">Logout</NuxtLink>
        </nav>
      </header>
  
      <!-- Main -->
      <main class="p-5 flex bg-yellow-100 flex-grow" > 
        
        <slot />
      </main>
  
      <!-- Footer -->
      <footer class="flex flex-row w-full bg-yellow-600 border-t-2 border-gray-400 items-center justify-center px-4 py-2 gap-4">
        <a href="https://www.youtube.com/watch?v=yEQvMMCGQ1Q" target="_blank" rel="noopener">
          <img src="/assets/images/youtube.png" class="w-25 h-25" alt="YouTube" />
        </a>
        <a href="https://web.telegram.org" target="_blank" rel="noopener">
          <img src="/assets/images/telegram.png" class="w-25 h-25" alt="Telegram" />
        </a>
        <a href="https://www.instagram.com" target="_blank" rel="noopener">
          <img src="/assets/images/instagram.png" class="w-25 h-25" alt="Instagram" />
        </a>
      </footer>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import { useHead } from '#app'
  
  const burger = ref(false)
  
  const switchBurger = () => {
    burger.value = !burger.value
  }
  
  useHead({ 
    script: [
      {
        async: true,
        src: 'https://www.googletagmanager.com/gtag/js?id=G-ME6FWYJMZC',
      },
      {
        innerHTML: `
          window.dataLayer = window.dataLayer || [];
          function gtag(){dataLayer.push(arguments);}
          gtag('js', new Date());
          gtag('config', 'G-ME6FWYJMZC');
        `,
        type: 'text/javascript',
        id: 'gtag',
      },
    ],
    __dangerouslyDisableSanitizersByTagID: {
      gtag: ['innerHTML'],
    },
  })
  </script>