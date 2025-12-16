<template>
    <div class="checkout-page-container">
        <h1>Ödeme Sayfası</h1>
        <p>Sepet ve ödeme işlemleri burada olacak.</p>
    </div>
</template>

<script setup lang="ts">
// Sayfa başlığını ayarlayalım
useHead({
    title: 'Watsons Clone - Ödeme'
})
</script>

<style scoped>
.checkout-page-container {
    padding: 40px 140px;
    /* Header ve Footer arasına boşluk bırakır */
    min-height: 500px;
    /* Footer'ın hemen yukarı yapışmasını engeller */
}

/* Mobilde kenar boşluklarını daralt */
@media (max-width: 768px) {
    .checkout-page-container {
        padding: 20px;
    }
}
</style>