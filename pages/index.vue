<template>
    <header class="flex flex-row w-full p-4 bg-gray-200">
        <div class="basis-1/4 items-center justify-start">
            <img src="/assets/images/download.png" class="w-16 h-16 bg-transparent" />
        </div>
        <div class="basis-1/4"></div>
        <div class="basis-1/2 flex flex-row gap-4 justify-end items-center">
            <NuxtLink to="/" class="p-2 hover:bg-gray-500">Home</NuxtLink>
            <NuxtLink to="/Lab3" class="p-2 hover:bg-gray-500">Lab3</NuxtLink>
            <NuxtLink to="#" class="p-2 hover:bg-gray-500">LogIn</NuxtLink>
            <NuxtLink to="#" class="p-2 hover:bg-gray-500">LogOut</NuxtLink>
        </div>
    </header>

    <main class = "p-5 flex bg-green-100 h-screen">
        <slot />
    </main>

    <footer class="flex flex-row w-full bg-green-400 border-t-2 border-gray-400 items-center justify-center px-4 py-2 gap-4">
        <a href = "www.youtube.com/watch?v=yEQvMMCGQ1Q"><img src="/assets/images/youtube.png" class="w-16 h-16"></a>
        <a href = "web.telegram.org"><img src="/assets/images/telegram.png" class = "w-16 h-16"></a>
        <a href = "www.instagram.com"><img src="/assets/images/instagram.png" class ="w-16 h-16 bg-transparent"></a>
    </footer>
</template>

<script setup>
import { useHead } from '#app';

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
});
</script>  
