<template>
  <div>
    <HeroBanner />
    <FeaturedProductsSection />
    <NewsletterBanner />
    <NiveaBanner />
    <FeaturedCategoriesSection />
  </div>
</template>

<script setup lang="ts">
import HeroBanner from '../components/HeroBanner.vue'
import FeaturedProductsSection from '../components/FeaturedProductsSection.vue'
import NewsletterBanner from '../components/NewsletterBanner.vue'
import NiveaBanner from '../components/NiveaBanner.vue'
import FeaturedCategoriesSection from '../components/FeaturedCategoriesSection.vue'

useHead({
  title: 'Watsons'
})
</script>