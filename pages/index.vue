<template>
    <div>
      <!-- Header -->
      <header class="flex flex-wrap justify-between items-center py-4 px-4 md:px-8 bg-white shadow-md">
        <!-- Logo and Mobile Menu Button -->
        <div class="flex items-center justify-between w-full md:w-auto">
          <button 
            @click="toggleMenu"
            class="bg-gray-200 px-2 py-1 rounded mr-4 md:hidden"
            aria-label="Toggle Menu"
          >
            <span class="text-xl font-semibold">☰</span>
          </button>
          <div class="font-bold text-gray-700 text-lg cursor-pointer">All Product & Services</div>
        </div>
  
        <!-- Navigation Links -->
        <nav
          :class="{'hidden': !isMenuOpen, 'flex': isMenuOpen}"
          class="flex-col md:flex md:flex-row md:space-x-6 md:items-center w-full md:w-auto mt-4 md:mt-0"
        >
          <a href="#" class="block text-gray-600 hover:text-gray-900 py-2 md:py-0">New Smartphones</a>
          <a href="#" class="block text-gray-600 hover:text-gray-900 py-2 md:py-0">Repair Services</a>
          <a href="#" class="block text-gray-600 hover:text-gray-900 py-2 md:py-0">Accessories</a>
          <a href="#" class="block text-gray-600 hover:text-gray-900 py-2 md:py-0">Popular Brands</a>
        </nav>
      </header>
  
      <!-- Hero Section -->
      <section
        class="bg-gradient-to-r from-gray-300 to-gray-400 p-6 md:p-8 rounded-lg m-4 md:m-8 flex flex-col md:flex-row items-center"
      >
        <div class="w-full md:w-1/2 mb-6 md:mb-0 text-center md:text-left">
          <h1 class="text-4xl md:text-5xl font-bold mb-4 text-gray-800">
            Buy & Sell Your Smartphones Hassle Free!
          </h1>
          <p class="text-gray-600 mb-6">
            Upgrade to the latest smartphones or sell your old device at unbeatable prices.
          </p>
          <button class="bg-green-500 text-white px-6 py-3 rounded hover:bg-green-600">
            Shop Now
          </button>
        </div>
        <div class="w-full md:w-1/2">
          <video
            src="/videos/iphone.mp4"
            class="rounded-lg w-full shadow-md"
            autoplay
            loop
            muted
            playsinline
          ></video>
        </div>
      </section>
  
      <!-- Categories Section -->
      <section class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-6 gap-4 px-4 md:px-8 mb-12">
        <div class="flex flex-col items-center justify-center p-4 border rounded-lg hover:shadow-md">
          <div class="text-green-500 text-4xl">📱</div>
          <p class="mt-2 text-gray-700 font-semibold">Mobile</p>
        </div>
        <div class="flex flex-col items-center justify-center p-4 border rounded-lg hover:shadow-md">
          <div class="text-green-500 text-4xl">📟</div>
          <p class="mt-2 text-gray-700 font-semibold">Tablet</p>
        </div>
        <div class="flex flex-col items-center justify-center p-4 border rounded-lg hover:shadow-md">
          <div class="text-green-500 text-4xl">⌚</div>
          <p class="mt-2 text-gray-700 font-semibold">SmartWatch</p>
        </div>
        <div class="flex flex-col items-center justify-center p-4 border rounded-lg hover:shadow-md">
          <div class="text-green-500 text-4xl">🎧</div>
          <p class="mt-2 text-gray-700 font-semibold">HeadPhones</p>
        </div>
        <div class="flex flex-col items-center justify-center p-4 border rounded-lg hover:shadow-md">
          <div class="text-green-500 text-4xl">🎮</div>
          <p class="mt-2 text-gray-700 font-semibold">Gaming</p>
        </div>
        <div class="flex flex-col items-center justify-center p-4 border rounded-lg hover:shadow-md">
          <div class="text-green-500 text-4xl">💻</div>
          <p class="mt-2 text-gray-700 font-semibold">Laptop</p>
        </div>
      </section>
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  
  const isMenuOpen = ref(false);
  
  function toggleMenu() {
    isMenuOpen.value = !isMenuOpen.value;
  }
  </script>
  
  <style scoped>
  /* Add any specific styles if needed */
  </style>
  