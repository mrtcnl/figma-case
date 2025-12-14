<template>
  <main class="home-page-container">
    <h1>3. Index.vue Sayfası Çalışıyor!</h1>
    <p>Burası ana içerik alanı.</p>
  </main>
</template>

<script setup lang="ts">
// Boş kalabilir
</script>

<style scoped>
.home-page-container {
  padding: 1rem;
  max-width: 100%;
  margin: 0 auto;
  background-color: #e0f7fa;
  /* Sayfanın yerini belli etmek için renk */
}

@media (min-width: 768px) {
  .home-page-container {
    padding: 2rem;
  }
}
</style>