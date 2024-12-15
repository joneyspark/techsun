<template>
    <header class="flex items-center justify-between p-4 border-b shadow-sm">
      <!-- Left Section: Logo -->
      <div class="flex items-center">
        <img src="/images/logo.png" alt="Logo" class="h-8 w-auto" />
        <span class="ml-2 font-bold text-xl text-green-600">
          Tech<span class="text-black">Sun</span>
        </span>
      </div>
  
      <!-- Middle Section: Search Bar -->
      <div
        :class="[
          'relative flex-1 mx-8 hidden md:block',
          isSearchOpen ? 'block' : 'hidden',
        ]"
      >
        <input
          v-show="!isSmallScreen || isSearchOpen"
          type="text"
          placeholder="What are you looking for?"
          class="w-full px-4 py-2 border rounded-full bg-gray-100 focus:outline-none"
        />
        <span class="absolute right-3 top-2.5 text-gray-400">
          🔍 <!-- Replace with proper Search Icon -->
        </span>
      </div>
  
      <!-- Right Section: Icons -->
      <div class="flex items-center space-x-4 md:space-x-6">
        <button
          aria-label="Search"
          class="md:hidden text-gray-600"
          @click="toggleSearch"
        >
          🔍 <!-- Mobile search icon -->
        </button>
        <button aria-label="Wishlist">
          ❤️ <!-- Replace with a proper Heart Icon -->
        </button>
        <button aria-label="Cart">
          🛒 <!-- Replace with a Cart Icon -->
        </button>
        <button aria-label="Profile">
          👤 <!-- Replace with a Profile Icon -->
        </button>
      </div>
  
      <!-- Full-width Search Bar for Small Screens -->
      <div
        v-if="isSearchOpen && isSmallScreen"
        class="absolute top-0 left-0 w-full bg-white p-4 shadow-lg flex items-center"
      >
        <input
          type="text"
          placeholder="What are you looking for?"
          class="w-full px-4 py-2 border rounded-full bg-gray-100 focus:outline-none"
        />
        <button @click="toggleSearch" class="ml-2 text-gray-600">✖️</button>
      </div>
    </header>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from "vue";
  
  // State to handle search visibility on small screens
  const isSearchOpen = ref(false);
  const isSmallScreen = ref(false);
  
  // Function to toggle the search bar on small screens
  const toggleSearch = () => {
    isSearchOpen.value = !isSearchOpen.value;
  };
  
  // Function to check screen size
  const handleResize = () => {
    isSmallScreen.value = window.innerWidth < 768; // Set breakpoint for small screens
  };
  
  // Add event listener for window resize
  onMounted(() => {
    handleResize();
    window.addEventListener("resize", handleResize);
  });
  
  onUnmounted(() => {
    window.removeEventListener("resize", handleResize);
  });
  </script>
  
  <style scoped>
  /* Custom styles if needed */
  </style>
  