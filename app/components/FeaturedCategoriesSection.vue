<template>
    <div class="featured-categories-container">
        <div class="featured-categories-top-container">
            <div class="featured-categories-line"></div>
            <h1 class="featured-categories-title">Featured categories</h1>
            <div class="featured-categories-line"></div>
        </div>

        <div class="featured-categories-grid">

            <div v-for="category in categories" :key="category.id" class="category-card"
                :style="{ backgroundImage: `url(${category.image})` }">
                <div class="category-content">
                    <h3 class="category-name">{{ category.title }}</h3>
                    <p class="category-desc">{{ category.description }}</p>
                    <button class="category-btn">BROWSE</button>
                </div>
            </div>

        </div>

    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

import cat1 from '../assets/images/categories/category1.jpg'
import cat2 from '../assets/images/categories/category2.jpg'
import cat3 from '../assets/images/categories/category3.jpg'
import cat4 from '../assets/images/categories/category4.jpg'

const categories = ref([
    {
        id: 1,
        title: 'Personal Care',
        description: 'Lorem ipsum dolor sit amet consectetu elit aliquam',
        image: cat1
    },
    {
        id: 2,
        title: 'Skin Care',
        description: 'Lorem ipsum dolor sit amet consectetu elit aliquam',
        image: cat2
    },
    {
        id: 3,
        title: 'Make - Up',
        description: 'Lorem ipsum dolor sit amet consectetu elit aliquam',
        image: cat3
    },
    {
        id: 4,
        title: 'Mother & Baby',
        description: 'Lorem ipsum dolor sit amet consectetu elit aliquam',
        image: cat4
    }
])
</script>

<style scoped>
.featured-categories-container {
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 0;
    display: flex;
    flex-direction: column;
    gap: 40px;
}

.featured-categories-top-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 32px;
}

.featured-categories-line {
    width: 100%;
    border-bottom: #0099A81A 1px solid;
}

.featured-categories-title {
    font-family: 'Roboto', sans-serif;
    font-weight: 500;
    font-size: 24px;
    color: #0099A8;
    white-space: nowrap;
    margin: 0;
}

.featured-categories-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 30px;
}

.category-card {
    width: 360px;
    height: 280px;
    background-color: #eee;
    background-size: cover;
    background-position: center;
    border-radius: 6px;
    position: relative;
    overflow: hidden;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto;
    border: 1px solid #ECECEC80
}

.category-content {
    background-color: rgba(255, 255, 255, 0.90);
    padding: 24px;
    text-align: center;
    border-radius: 6px;
    width: 70%;
    opacity: 0;
    transform: translateY(10px);
    transition: all 0.4s ease;
    display: flex;
    flex-direction: column;
    gap: 8px;
    align-items: center;
}

.category-card:hover .category-content {
    opacity: 1;
    transform: translateY(0);
}

.category-name {
    font-weight: 700;
    font-size: 20px;
    line-height: 24px;
    letter-spacing: 0px;
    text-align: center;
    vertical-align: middle;
    margin: 0;
}

.category-desc {
    font-weight: 400;
    font-size: 14px;
    line-height: 24px;
    letter-spacing: 0px;
    text-align: center;
    vertical-align: middle;
    margin: 0;
}

.category-btn {
    background-color: #0099A8;
    color: white;
    border: none;
    font-weight: 700;
    font-size: 12px;
    border-radius: 4px;
    cursor: pointer;
    text-transform: uppercase;
    width: 90px;
    height: 32px;
}

.category-btn:hover {
    background-color: #007d8a;
}

@media (max-width: 768px) {
    .featured-categories-container {
        width: 100%;
        margin: 0 auto;
        padding: 16px;
        display: flex;
        flex-direction: column;
        gap: 16px;
    }

    .featured-categories-title {
        font-size: 20px;
    }

    .featured-categories-grid {
        grid-template-columns: 1fr;
    }

    .category-card {
        height: 232px;
    }

    .category-content {
        opacity: 1;
        transform: translateY(0px);
    }
}
</style>