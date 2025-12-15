<template>
    <div class="nivea-banner-container">
        <img class="nivea-banner-img1" src="../assets//images/nivea-banner/nivea-img1.png" alt="">
        <div class="nivea-banner-text-container">

        </div>
        <img class="nivea-banner-img2" src="../assets//images/nivea-banner/nivea-img2.png" alt="">
    </div>
</template>

<style scoped>
.nivea-banner-container {
    width: 100%;
    height: 400px;
    background-image:
        linear-gradient(0deg, rgba(19, 138, 150, 0.3), rgba(19, 138, 150, 0.3)),
        linear-gradient(88.28deg, rgba(16, 160, 174, 0.3) 14.56%, rgba(98, 214, 225, 0.3) 56.19%, rgba(21, 166, 181, 0.3) 98.69%),
        url('../assets/images/nivea-banner/nivea-bg.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}

.nivea-banner-text-container {
    width: 274px;
    height: 246px;
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-bottom: 51px;
    padding: 32px;
    border-top-left-radius: 40px;
    border-bottom-right-radius: 40px;
    background-color: #FFFFFF;
}

.nivea-banner-img1 {
    height: 292px;
    position: absolute;
    top: 75px;
    left: 175px;
}

.nivea-banner-img2 {
    height: 294px;
    position: absolute;
    top: 51px;
    right: 200px;
}
</style>