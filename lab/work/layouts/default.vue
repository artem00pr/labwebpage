<template>
  <header class="flex flex-row w-full bg-green-400 border-b-2 border-gray-400 max-sm:justify-between max-sm:relative">
    <div class="basis-1/4 items-center justify-start px-8 min-w-40 max-sm:basis-auto">
      <img src="assets/images/arizona.png" class="w-16 h-16 bg-transparent">
    </div>

    <div class="basis-1/4 max-sm:basis-auto"></div>

    <nav class="basis-1/2 flex flex-row items-center justify-end px-8 gap-4 max-sm:basis-auto max-sm:absolute max-sm:top-full max-sm:w-full
      max-sm:justify-center max-sm:flex-col max-sm:gap-0 max-sm:bg-white max-sm:px-0">
      <NuxtLink to="/" class="my-auto p-2 hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:border-b-2 max-sm:text-center">
        Home
      </NuxtLink>

      <!-- Labs Dropdown Menu -->
      <div class="relative my-auto p-2 hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center"
           @click="toggleSubmenu">
        Labs
        <div v-show="showSubmenu" class="flex flex-col absolute top-full bg-white text-black w-56 text-center shadow-md">
          <NuxtLink to="/lab3" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white">Lab3</NuxtLink>
          <NuxtLink to="/lab4" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white">Lab4</NuxtLink>
          <NuxtLink to="/lab5" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white">Lab5</NuxtLink>
          <NuxtLink to="/lab6" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white">Lab6</NuxtLink>
        </div>
      </div>

      <NuxtLink to="/login" class="my-auto p-2 hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">LogIn</NuxtLink>
      <NuxtLink to="/logout" class="my-auto p-2 hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">LogOut</NuxtLink>
    </nav>
  </header>

  <main class="p-5 flex bg-green-100 h-screen">
    <slot />
  </main>

  <footer class="flex flex-row w-full bg-green-400 border-t-2 border-gray-400 items-center justify-center px-4 py-2 gap-4">
    <a href="https://www.youtube.com/"><img src="assets/images/youtube.png" class="w-16 h-16"></a>
    <a href="https://github.com/"><img src="assets/images/github.png" class="w-16 h-16"></a>
    <a href="https://www.facebook.com/"><img src="assets/images/facebook.png" class="w-16 h-16 bg-transparent"></a>
  </footer>
</template>

<script setup>
import { ref } from 'vue';

const showSubmenu = ref(false);

const toggleSubmenu = () => {
  showSubmenu.value = !showSubmenu.value;
};
</script>
