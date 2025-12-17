<template>
    <div class="carousel-container-mobile" :style="{ background: slideBackgrounds[currentSlide] }">

        <div class="slider-track" :style="{ transform: `translateX(-${currentSlide * 100}%)` }">

            <div v-for="(slide, index) in slides" :key="index" class="slide-item">
                <div class="container hero-inner">

                    <div class="hero-content">
                        <span class="brand-tag">{{ slide.tag }}</span>
                        <h2 class="hero-title">{{ slide.title }}</h2>
                        <p class="hero-desc">{{ slide.description }}</p>
                        <button class="shop-btn">SHOP NOW</button>
                        <div class="dots-container">
                            <span v-for="(slide, index) in slides" :key="'dot-' + index" class="dot"
                                :class="{ active: currentSlide === index }" @click="goToSlide(index)"></span>
                        </div>
                    </div>

                    <div class="hero-image">
                        <div class="hero-circle circle-front"></div>
                        <div class="hero-circle circle-back"></div>

                        <img src="../assets/images/carousel-images/cr-img1.png" class="hero-banner-img1"
                            alt="slide.title" />
                        <img src="../assets/images/carousel-images/cr-img2.png" class="hero-banner-img2"
                            alt="slide.title" />
                        <img src="../assets/images/carousel-images/cr-img3.png" class="hero-banner-img3"
                            alt="slide.title" />
                        <img src="../assets/images/carousel-images/cr-img4.png" class="hero-banner-img4"
                            alt="slide.title" />


                    </div>

                </div>
            </div>

        </div>

        <button class="arrow left-arrow" @click="prevSlide">
            <Icon name="fa-solid:chevron-left" />
        </button>
        <button class="arrow right-arrow" @click="nextSlide">
            <Icon name="fa-solid:chevron-right" />
        </button>

    </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const slides = [
    {
        tag: 'NATURALS BY WATSONS',
        title: 'The new 2021 collection',
        description: 'Known as "the miracle plant", Aloe Vera helps to nourish, moisturize and keep the hair looking smooth.',
    },
    {
        tag: 'SUMMER SALE',
        title: '%50 Discount on Skin Care',
        description: 'Get the best skin care products with amazing summer discounts. Protect your skin now.',
    },
    {
        tag: 'NEW ARRIVALS',
        title: 'Organic & Pure Beauty',
        description: 'Discover the power of nature with our new organic product line. %100 Vegan.',
    }
]

const currentSlide = ref(0)
let autoPlayInterval: any = null

const nextSlide = () => {
    if (currentSlide.value === slides.length - 1) {
        currentSlide.value = 0
    } else {
        currentSlide.value++
    }
}

const prevSlide = () => {
    if (currentSlide.value === 0) {
        currentSlide.value = slides.length - 1
    } else {
        currentSlide.value--
    }
}

const goToSlide = (index: number) => {
    currentSlide.value = index
}

onMounted(() => {
    autoPlayInterval = setInterval(nextSlide, 5000)
})

onUnmounted(() => {
    clearInterval(autoPlayInterval)
})

const slideBackgrounds = [
    `linear-gradient(0deg, #F2F0FF, #F2F0FF), 
   linear-gradient(87.81deg, #F2F0FF 35.04%, rgba(255, 255, 255, 0.67) 53.63%, rgba(252, 252, 255, 0.96) 64.78%, #F2F0FF 90.91%)`,

    `linear-gradient(0deg, #FFF3E0, #FFF3E0), 
   linear-gradient(87.81deg, #FFF3E0 35.04%, rgba(255, 255, 255, 0.67) 53.63%, rgba(255, 248, 225, 0.96) 64.78%, #FFF3E0 90.91%)`,

    `linear-gradient(0deg, #E8F5E9, #E8F5E9), 
   linear-gradient(87.81deg, #E8F5E9 35.04%, rgba(255, 255, 255, 0.67) 53.63%, rgba(232, 245, 233, 0.96) 64.78%, #E8F5E9 90.91%)`
]
</script>

<style scoped>
.carousel-container-mobile {
    width: 100%;
    height: 400px;
    position: relative;
    overflow: hidden;
    transition: all 0.8s ease-in-out;
}

.slider-track {
    display: flex;
    height: 100%;
    transition: transform 0.5s ease-in-out;
    width: 100%;
}

.slide-item {
    min-width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.container {
    margin: 0 auto;
    padding: 0 140px;
}

.hero-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
}

.hero-content {
    flex: 1;
    max-width: 500px;
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.brand-tag {
    font-weight: 700;
    font-size: 14px;
    line-height: 16px;
    letter-spacing: 0px;
    vertical-align: middle;
    text-transform: uppercase;
    color: #8493A8;
}

.hero-title {
    font-weight: 700;
    font-size: 34px;
    line-height: 48px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #2A2A48;
    margin: 0;
}

.hero-desc {
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #485363;
    margin: 0;
}

.shop-btn {
    background-color: #FF27AD;
    color: white;
    border: none;
    font-weight: bold;
    cursor: pointer;
    border-radius: 4px;
    width: 105px;
    height: 32px;
}

.hero-image {
    width: 580px;
    height: 400px;
    position: relative;
}

.hero-image img {
    position: absolute;
    object-fit: contain;
}

.hero-banner-img1 {
    width: 334px;
    height: 314px;
    top: 20px;
    left: 0;
    z-index: 1;
}

.hero-banner-img2 {
    width: 256px;
    height: 256px;
    top: 130px;
    left: 81px;
    z-index: 5;
}

.hero-banner-img3 {
    width: 336px;
    height: 336px;
    top: 27px;
    left: 126px;
    z-index: 3;
}

.hero-banner-img4 {
    width: 101px;
    height: 326px;
    top: 36px;
    left: 361px;
    z-index: 4;
}

.hero-circle {
    position: absolute;
    border-radius: 50%;
    background-color: #0099A81A;
    z-index: 0;
}

.circle-front {
    width: 326.75px;
    height: 326.35px;
    top: 20.65px;
    right: 0px;
    transform: rotate(0deg);
    opacity: 1;
}

.circle-back {
    width: 328.26px;
    height: 327.86px;
    top: 40px;
    right: 27.73px;
    transform: rotate(0deg);
    opacity: 1;
}

.arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    border: none;
    width: 48px;
    height: 48px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #333;
    font-size: 32px;
    z-index: 10;
    background: none;
}

.arrow:hover {
    color: #ff0099;
}

.left-arrow {
    left: 20px;
}

.right-arrow {
    right: 20px;
}

.dots-container {
    display: flex;
    align-items: center;
    gap: 8px;
}

.dot {
    width: 6px;
    height: 6px;
    background-color: #ccc;
    border-radius: 50%;
    cursor: pointer;
    transition: background-color 0.3s;
}

.dot.active {
    background-color: #2e1053;
    width: 8px;
    height: 8px;
}

.carousel-container-mobile {
    display: none;
}

@media (max-width: 768px) {
    .hero-inner {
        flex-direction: column-reverse;
        text-align: center;
    }

    .hero-content {
        margin-top: 20px;
    }

    .hero-image img {
        max-height: 250px;
    }

    .hero-title {
        font-size: 2rem;
    }

    .carousel-container-mobile {
        display: flex;
        height: auto;
        padding-bottom: 16px;
    }

    .arrow {
        display: none;
    }

    .container {
        margin: 0 auto;
        padding: 16px;
    }

    .hero-content {
        flex: 1;
        max-width: 500px;
        display: flex;
        flex-direction: column;
        align-items: start;
        text-align: start;
        gap: 16px;
    }

    .brand-tag {
        font-size: 12px;
    }

    .hero-title {
        font-size: 24px;
        line-height: 32px;
    }

    .shop-btn {
        width: 100%;
    }

    .hero-image {
        width: 375px;
        height: 295px;
        position: relative;
    }

    .hero-image img {
        position: absolute;
        object-fit: contain;
    }

    .hero-banner-img1 {
        width: 216px;
        height: 203px;
        top: 27px;
        left: 10px;
        z-index: 1;
    }

    .hero-banner-img2 {
        width: 166px;
        height: 166px;
        top: 97px;
        left: 62px;
        z-index: 5;
    }

    .hero-banner-img3 {
        width: 218px;
        height: 217px;
        top: 31px;
        left: 91px;

        z-index: 3;
    }

    .hero-banner-img4 {
        width: 66px;
        height: 211px;
        top: 37px;
        left: 243px;
        z-index: 4;
    }

    .hero-circle {
        position: absolute;
        border-radius: 50%;
        background-color: #0099A81A;
        z-index: 0;
    }

    .circle-front {
        width: 264px;
        height: 257px;
        top: 10px;
        right: 25px;
        transform: rotate(0deg);
        opacity: 1;
    }

    .circle-back {
        width: 264px;
        height: 257px;
        top: 30px;
        right: 50px;
        transform: rotate(0deg);
        opacity: 1;
    }

    .dots-container {
        margin: 0 auto;
    }
}
</style>