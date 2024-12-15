<template>
    <div>
      <HeaderView />
      <main class="min-h-screen">
        <slot />
      </main>
      <FooterView />
    </div>
  </template>
  
  <script setup>
  import HeaderView from '~/components/HeaderView.vue';
  import FooterView from '~/components/FooterView.vue';
  </script>
  
  <style>
  /* Global layout styles */
  </style>
  