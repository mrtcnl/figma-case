<template>
    <div class="newsletter-banner-container">
        <div class="newsletter-banner-left-container">
            <h2>Sign up to our newsletter</h2>
            <h3>Be the first to hear about the latest offers.</h3>
        </div>
        <div class="newsletter-banner-right-container">
            <input class="newsletter-input" type="text" placeholder="Your email address">
            <button class="newsletter-button">SUBSCRIBE</button>
        </div>
    </div>
</template>

<style scoped>
.newsletter-banner-container {
    width: 100%;
    height: 144px;
    padding: 40px 140px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #F2F0FF;
}

.newsletter-banner-left-container {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.newsletter-banner-left-container h2 {
    font-weight: 700;
    font-size: 24px;
    line-height: 32px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #2A2A48;
    margin: 0;
}

.newsletter-banner-left-container h3 {
    font-weight: 400;
    font-size: 16px;
    line-height: 16px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #2A2A4899;
    margin: 0;
}

.newsletter-banner-right-container {
    display: flex;
    justify-content: space-between;
    gap: 16px;
}

.newsletter-input {
    width: 412px;
    height: 48px;
    padding: 16px;
    border: 1px solid #ECECEC;
    border-radius: 4px;
    font-size: 16px;
    color: #333333;
}

.newsletter-button {
    width: 132px;
    height: 48px;
    border-radius: 4px;
    padding-right: 16px;
    padding-left: 16px;
    gap: 8px;
    opacity: 1;
    color: white;
    background-color: #FF27AD;
    border: none;
    font-size: 14px;
    font-weight: 700;
}

.newsletter-button:hover {
    background-color: #e0209a;
    cursor: pointer;
}

@media (max-width: 768px) {
    .newsletter-banner-container {
        width: 100%;
        padding: 16px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: start;
        gap: 16px;
    }

    .newsletter-banner-left-container {
        gap: 8px;
    }

    .newsletter-banner-left-container h2 {
        font-weight: 700;
        font-size: 20px;
        line-height: 24px;
    }

    .newsletter-banner-left-container h3 {
        font-size: 14px;
        line-height: 16px;
    }

    .newsletter-input {
        width: 60%;
        height: 48px;
        padding: 16px;
        border: 1px solid #ECECEC;
        border-radius: 4px;
        font-size: 16px;
        color: #333333;
    }
}
</style>