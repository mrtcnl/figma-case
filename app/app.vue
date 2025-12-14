<template>
  <div class="main-layout">
    <AppHeader />
    <main>
      <HeroBanner />
      <FeaturedProductsSection />
    </main>
  </div>
</template>

<script setup lang="ts">
import AppHeader from '../components/AppHeader.vue'

useHead({
  title: 'Watsons Clone - Anasayfa',
  link: [
    { rel: 'preconnect', href: 'https://fonts.googleapis.com' },
    { rel: 'preconnect', href: 'https://fonts.gstatic.com', crossorigin: '' },
    { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap' }
  ]
})
</script>

<style>

body {
  margin: 0;
  padding: 0;
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  color: #333;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}
</style>