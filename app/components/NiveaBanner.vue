<template>
    <div class="nivea-banner-container">
        <img class="nivea-banner-img1" src="../assets/images/nivea-banner/nivea-img1.png" alt="">

        <div class="nivea-banner-text-container">
            <div class="banner-text-group">
                <span class="banner-subtitle">EN SEVDİĞİNİZ ÜRÜNLER</span>
                <span class="banner-slogan">TEK TIKLA KAPINIZDA!</span>
            </div>

            <div class="banner-discount-group">
                <span class="discount-percent">60 %</span>
                <span class="discount-label">DISCOUNT</span>
            </div>

            <button class="banner-btn">SHOP NOW</button>
        </div>

        <img class="nivea-banner-img2" src="../assets/images/nivea-banner/nivea-img2.png" alt="">
    </div>
</template>

<style scoped>
.nivea-banner-container {
    width: 100%;
    height: 400px;
    /* Arkaplan ayarların */
    background-image:
        linear-gradient(0deg, rgba(19, 138, 150, 0.3), rgba(19, 138, 150, 0.3)),
        linear-gradient(88.28deg, rgba(16, 160, 174, 0.3) 14.56%, rgba(98, 214, 225, 0.3) 56.19%, rgba(21, 166, 181, 0.3) 98.69%),
        url('../../assets/images/nivea-banner/nivea-bg.png');
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
    z-index: 10;
}

.banner-text-group {
    display: flex;
    flex-direction: column;
    gap: 4px;
}

.banner-subtitle {
    font-weight: 400;
    font-size: 16px;
    line-height: 16px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #00106B;
}

.banner-slogan {
    font-weight: 700;
    font-size: 20px;
    line-height: 24px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #00106B;
}

.banner-discount-group {
    display: flex;
    flex-direction: column;
    line-height: 1;
}

.discount-percent {
    font-family: Rubik;
    font-weight: 700;
    font-size: 48px;
    line-height: 48px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #00106B;
}

.discount-label {
    font-family: Rubik;
    font-weight: 700;
    font-size: 34px;
    line-height: 34px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #00106B;
}

.banner-btn {
    background-color: #0099A8;
    color: white;
    width: 105px;
    height: 32px;
    font-weight: 700;
    font-size: 14px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background 0.3s;
}

.banner-btn:hover {
    background-color: #007d8a;
}

.nivea-banner-img1 {
    height: 292px;
    position: absolute;
    top: 75px;
    left: 175px;
    z-index: 5;
}

.nivea-banner-img2 {
    height: 294px;
    position: absolute;
    top: 51px;
    right: 200px;
    z-index: 5;
}

media 
</style>