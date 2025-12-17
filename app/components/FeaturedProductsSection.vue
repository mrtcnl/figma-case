<template>
    <div class="featured-section-container">
        <div class="featured-section-top-container">
            <div class="featured-section-line"></div>
            <h1 class="featured-section-title">Featured products</h1>
            <div class="featured-section-line"></div>
        </div>

        <div class="featured-section-bottom-container">

            <div v-for="product in products" :key="product.id" class="product-card">

                <div class="product-image-wrapper">
                    <img :src="product.image" :alt="product.title" class="product-img" />

                    <div class="product-actions">
                        <button class="action-btn">
                            <Icon name="fa-solid:eye" size="16" />
                            <span>Quick View</span>
                        </button>
                        <div class="action-divider"></div>
                        <button class="action-btn">
                            <Icon name="fa-solid:shopping-basket" size="16" />
                            <span>Add</span>
                        </button>
                    </div>
                </div>

                <div class="product-info">
                    <div class="product-price">{{ product.price }} TL</div>
                    <div class="product-title">{{ product.title }}</div>
                </div>

                <div class="mobile-add-btn">
                    <button>
                        <Icon name="fa-solid:shopping-basket" size="16" />
                        ADD
                    </button>
                </div>

            </div>

        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

import img1 from '../assets/images/featured-products/featured1.png'
import img2 from '../assets/images/featured-products/featured2.png'
import img3 from '../assets/images/featured-products/featured3.png'
import img4 from '../assets/images/featured-products/featured4.png'

const products = ref([
    {
        id: 1,
        image: img1,
        price: '44,95',
        title: 'Herbal Science Boom Butter Hair Care Oil 190 ml'
    },
    {
        id: 2,
        image: img2,
        price: '42,25',
        title: 'Diadermine Lift + Serum Booster Vitamin C'
    },
    {
        id: 3,
        image: img3,
        price: '29,45',
        title: 'Ashley Joy Strengthening Shampoo 400ml'
    },
    {
        id: 4,
        image: img4,
        price: '28,95',
        title: 'Herbal Extract Refreshing Shampoo 400ml'
    }
])
</script>

<style scoped>
.featured-section-container {
    padding: 40px 140px;
    display: flex;
    flex-direction: column;
    gap: 40px;
}

.featured-section-top-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 32px;
}

.featured-section-line {
    width: 100%;
    border-bottom: #0099A81A 1px solid;
}

.featured-section-title {
    font-weight: 500;
    font-size: 24px;
    color: #0099A8;
    white-space: nowrap;
    margin: 0;
}

.featured-section-bottom-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 40px;
}

.product-card {
    background-color: #FFFFFF;
    border: 1px solid #ECECEC80;
    border-radius: 6px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-between;
    height: 328px;
    transition: box-shadow 0.3s ease;
    cursor: pointer;
    box-shadow: 0px 1px 8px 0px #0000000A;
    overflow: hidden;
}

.product-card:hover {
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    border-color: #e0e0e0;
}

.product-card:hover .product-actions {
    opacity: 1;
    transform: translateY(0);
}

.product-image-wrapper {
    width: 100%;
    height: 184px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #ECECEC29;
    position: relative;
}

.product-img {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
}

.product-actions {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 48px;
    background-color: #333333;
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    opacity: 0;
    transform: translateY(10px);
    transition: all 0.3s ease-in-out;
}

.action-btn {
    background: none;
    border: none;
    color: white;
    font-size: 14px;
    font-weight: 500;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 0 10px;
}

.action-btn:hover {
    color: #0099A8;
}

.action-divider {
    width: 1px;
    height: 20px;
    background-color: rgba(255, 255, 255, 0.2);
}

.product-info {
    display: flex;
    flex-direction: column;
    gap: 8px;
    padding: 32px;
}

.product-price {
    font-weight: 700;
    font-size: 20px;
    line-height: 24px;
    color: #2A2A48;
}

.product-title {
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    color: #485363;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
}

.mobile-add-btn {
    display: none;
}

@media (max-width: 768px) {
    .featured-section-container {
        padding: 16px;
        display: flex;
        flex-direction: column;
        gap: 16px;
    }

    .featured-section-title {
        font-weight: 500;
        font-size: 20px;
    }

    .featured-section-bottom-container {
        grid-template-columns: repeat(2, minmax(0, 1fr));
        gap: 16px;
    }

    .product-card {
        height: auto;
        gap: 8px;
    }

    .product-info {
        gap: 8px;
        padding: 16px;
    }

    .product-price {
        font-size: 16px;
        line-height: 16px;
    }

    .product-title {
        font-size: 14px;
        line-height: 24px;
    }

    .product-card:hover .product-actions {
        opacity: 0;
        transform: translateY(0);
    }

    .mobile-add-btn {
        display: flex;
        justify-content: center;
        padding: 16px;
        border: 1px solid #ECECEC80;
        width: 100%;
    }

    .mobile-add-btn button {
        width: 100%;
        height: 32;
        gap: 8px;
        opacity: 1;
        height: 32px;
        font-weight: 700;
        color: white;
        border-radius: 4px;
        background-color: #FF27AD;
        display: flex;
        align-items: center;
        justify-content: center;
    }
}
</style>