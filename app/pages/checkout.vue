<template>
    <div class="checkout-page-container">
        <div class="checkout-page-header">
            <div class="checkout-page-header-links">
                <a href="#" class="checkout-page-header-link">Homepage</a>
                <span class="checkout-page-header-separator">></span>
                <a href="#" class="checkout-page-header-link ">Shopping Cart</a>
                <span class="checkout-page-header-separator">></span>
                <a href="#" class="checkout-page-header-link active">Checkout</a>
            </div>
            <h1 class="checkout-page-header-title">Checkout</h1>
        </div>
        <div class="checkout-page-main-content">
            <div class="checkout-page-left-container">

            </div>
            <div class="checkout-page-right-container">
                
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
useHead({
    title: 'Watsons - Checkout'
})
</script>

<style scoped>
.checkout-page-container {
    min-height: 500px;
}

.checkout-page-header {
    padding: 24px 140px;
    display: flex;
    flex-direction: column;
    gap: 16px;
    background-color: #ECECEC4D;
}

.checkout-page-header-links {
    display: flex;
    align-items: center;
    gap: 8px;
}

.checkout-page-header-separator {
    font-size: 12px;
    color: Gray 40%;

}

.checkout-page-header-link {
    font-weight: 400;
    font-size: 12px;
    line-height: 16px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #8493A8;
    text-decoration: none;
}

.checkout-page-header-link.active {
    color: #0099A8;
}

.checkout-page-header-title {
    font-family: Rubik;
    font-weight: 500;
    font-size: 34px;
    line-height: 48px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #2A2A48;
    margin: 0;
}

.checkout-page-main-content {
    padding: 32px 140px;
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 40px;
}

.checkout-page-left-container {
    grid-column: span 2 / span 2;
}

.checkout-page-right-container {
    grid-column: span 1 / span 1;
}

@media (max-width: 768px) {
    .checkout-page-container {
        padding: 20px;
    }
}
</style>