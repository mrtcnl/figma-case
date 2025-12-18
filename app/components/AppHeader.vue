<template>
    <header class="app-header">

        <div class="header-top-bar">
            <div class="header-top-left-container">
                <button class="header-top-button">
                    <Icon name="fa7-solid:shop" size="20" />
                    <span>Stores</span>
                </button>
                <button class="header-top-button">
                    <Icon name="fa7-solid:book-open" size="20" />
                    <span>Catalog</span>
                </button>
            </div>
            <div class="header-top-mid-container">
                <span>Watsons Beauty and Personal Care Awards Nominees!</span>
            </div>
            <div class="header-top-right-container">
                <div class="header-top-button">
                    <span class="header-phone-number">Call us:(+90) 850 123 45 67</span>
                    <Icon name="fa7-solid:phone-alt" size="20" />
                </div>
            </div>
        </div>

        <div class="header-main-container">
            <div class="header-main-left-container">
                <a href="/" class="header-logo">
                    <img class="header-logo" src="~/assets/images/watsons-logo.png" alt="Watsons">
                </a>
            </div>

            <div class="header-main-right-container">
                <div class="search-bar-container">
                    <div class="search-bar-wrapper">
                        <Icon name="fa-solid:search" class="search-icon" size="18" />
                        <input type="text" placeholder="Write the product or category you are looking for" />
                    </div>
                </div>

                <div class="user-cart-container">
                    <div class="user-actions">
                        <div class="user-info">
                            <span class="greeting">Hello,</span>
                            <span class="username">Clara Clara</span>
                        </div>
                        <img src="~/assets/images/user-img.jpg" alt="Clara Clara" class="user-avatar" />
                        <Icon name="fa-solid:chevron-down" class="dropdown-icon" size="12" />
                    </div>
                    <div class="divider"></div>
                    <a href="/checkout">
                        <div class="cart-wrapper">
                            <Icon name="fa7-solid:basket-shopping" class="cart-icon" size="24" />
                            <span class="cart-badge">2</span>
                        </div>
                    </a>
                </div>
            </div>

            <div class="header-main-right-container-mobile">
                <button class="mobile-icon-btn">
                    <Icon name="fa-solid:search" size="20" color="#333" />
                </button>

                <a href="/checkout" class="mobile-icon-btn">
                    <div class="cart-wrapper">
                        <Icon name="fa7-solid:basket-shopping" class="cart-icon" size="22" />
                        <span class="cart-badge">2</span>
                    </div>
                </a>

                <button class="mobile-icon-btn" @click="toggleMenu">
                    <Icon name="fa-solid:bars" size="22" color="#333" />
                </button>
            </div>

        </div>

        <div class="header-nav-menu">
            <a class="header-nav-item" href="#">CAMPAIGNS</a>
            <a class="header-nav-item" href="#">PERSONAL CARE</a>
            <a class="header-nav-item" href="#">SKIN CARE</a>
            <a class="header-nav-item" href="#">MAKE - UP</a>
            <a class="header-nav-item" href="#">MOTHER & BABY</a>
            <a class="header-nav-item" href="#">MEN CARE</a>
            <a class="header-nav-item" href="#">HEALTHY LIFE</a>
            <a class="header-nav-item" href="#">BRANDS</a>
        </div>

        <div class="mobile-menu-overlay" v-if="isMenuOpen" @click="toggleMenu"></div>

        <div class="mobile-side-menu" :class="{ 'open': isMenuOpen }">

            <div class="mobile-menu-header">
                <button class="close-btn" @click="toggleMenu">
                    <Icon name="fa-solid:times" size="16" />
                </button>
                <span class="menu-title">Menu</span>
            </div>

            <div class="mobile-menu-list">
                <a href="#" class="mobile-menu-item">
                    <Icon name="fa-solid:chevron-left" size="12" class="arrow-icon" />
                    <span>Campaigns</span>
                </a>
                <a href="#" class="mobile-menu-item">
                    <Icon name="fa-solid:chevron-left" size="12" class="arrow-icon" />
                    <span>Personal Care</span>
                </a>
                <a href="#" class="mobile-menu-item">
                    <Icon name="fa-solid:chevron-left" size="12" class="arrow-icon" />
                    <span>Skin Care</span>
                </a>
                <a href="#" class="mobile-menu-item">
                    <Icon name="fa-solid:chevron-left" size="12" class="arrow-icon" />
                    <span>Make - up</span>
                </a>
                <a href="#" class="mobile-menu-item">
                    <Icon name="fa-solid:chevron-left" size="12" class="arrow-icon" />
                    <span>Mother & Baby</span>
                </a>
                <a href="#" class="mobile-menu-item">
                    <Icon name="fa-solid:chevron-left" size="12" class="arrow-icon" />
                    <span>Healthy Life</span>
                </a>
                <a href="#" class="mobile-menu-item">
                    <Icon name="fa-solid:chevron-left" size="12" class="arrow-icon" />
                    <span>Brands</span>
                </a>
            </div>

            <div class="mobile-menu-footer">
                <a href="#" class="mobile-footer-item">
                    <span>My profile</span>
                    <Icon name="fa-regular:user" size="18" />
                </a>
                <a href="#" class="mobile-footer-item">
                    <span>Order history</span>
                    <Icon name="fa7-solid:box-open" size="18" />
                </a>
                <a href="#" class="mobile-footer-item">
                    <span>Help center</span>
                    <Icon name="fa-regular:question-circle" size="18" />
                </a>
                <a href="#" class="mobile-footer-item logout">
                    <span>Log out</span>
                    <Icon name="fa-solid:sign-out-alt" size="18" />
                </a>
            </div>

        </div>

    </header>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value
    if (isMenuOpen.value) {
        document.body.style.overflow = 'hidden'
    } else {
        document.body.style.overflow = 'auto'
    }
}
</script>

<style scoped>
.header-top-bar {
    padding: 0 140px;
    height: 40px;
    background-color: #505357;
    color: white;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 14px;

}

.header-top-left-container {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: 10px;
    flex-grow: 1;
}

.header-top-mid-container {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-grow: 1;
    justify-content: center;

}

.header-top-right-container {
    flex-grow: 1;
    display: flex;
    align-items: center;
    justify-content: flex-end;
}

.header-top-mid-container span {
    font-weight: 400;
    font-size: 14px;
    line-height: 24px;
    letter-spacing: 0px;
    text-align: center;
    vertical-align: middle;
    color: #ECECEC80;

}

.header-top-button {
    background: none;
    border: none;
    color: white;
    padding: 0 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 14px;
    font-weight: 500;
}

.header-main-container {
    height: 72px;
    padding: 0 140px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.header-main-left-container {
    display: flex;
    align-items: center;
}

.header-main-right-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    gap: 24px;
}

.header-logo {
    height: 28px;
}

.search-bar-container {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.search-bar-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #f9f9f9;
    border-radius: 50px;
    padding: 10px 20px;
    width: 560px;
    border: 1px solid transparent;
}

.search-icon {
    color: #b0b0b0;
    margin-right: 10px;
}

.search-bar-wrapper input {
    border: none;
    background: transparent;
    outline: none;
    width: 100%;
    font-size: 14px;
    color: #333;
}

.user-cart-container {
    display: flex;
    align-items: center;
    gap: 24px;
}

.user-actions {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-left: 20px;
    cursor: pointer;
}

.user-info {
    display: flex;
    gap: 4px;
    font-size: 14px;
}

.greeting {
    color: #888;
}

.username {
    color: #333;
    font-weight: 600;
    text-wrap: nowrap;
}

.user-avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    object-fit: cover;
    border: 1px solid #eaeaea;
}

.dropdown-icon {
    color: #ccc;
    transition: transform 0.2s;
}

.user-actions:hover .dropdown-icon {
    color: #009da0;
}



.divider {
    width: 1px;
    height: 30px;
    background-color: #e0e0e0;
}

.cart-wrapper {
    position: relative;
    cursor: pointer;
    display: flex;
    align-items: center;
}

.cart-icon {
    color: #333;
}

.cart-badge {
    position: absolute;
    top: -8px;
    right: -8px;
    background-color: #ff3b30;
    color: white;
    font-size: 11px;
    font-weight: bold;
    width: 18px;
    height: 18px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px solid white;
}

.header-nav-menu {
    height: 48px;
    padding: 0 140px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid #eaeaea;
}

.header-nav-item {
    height: 100%;
    display: flex;
    align-items: center;
    padding: 0 16px;
    font-weight: 700;
    font-size: 14px;
    letter-spacing: 0px;
    text-transform: uppercase;
    text-decoration: none;
    color: #2A2A48;
    border-radius: 4px 4px 0 0;
    transition: all 0.2s ease;
}

.header-nav-item:hover {
    background-color: #ECECEC;
    color: #009da0;
}

.header-main-right-container-mobile {
    display: none;
}

.mobile-icon-btn {
    background: none;
    border: none;
    cursor: pointer;
    padding: 5px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.mobile-side-menu {
    position: fixed;
    top: 0;
    right: -320px;
    width: 300px;
    height: 100vh;
    background-color: white;
    z-index: 1000;
    transition: right 0.3s ease-in-out;
    display: flex;
    flex-direction: column;
    box-shadow: -2px 0 10px rgba(0, 0, 0, 0.1);
}

.mobile-side-menu.open {
    right: 0;
}

.mobile-menu-header {
    background-color: #F2F0FF;
    height: 56px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 20px;
}

.close-btn {
    background: none;
    border: none;
    cursor: pointer;
    font-size: 20px;
    color: #333;
    padding: 5px;
}

.menu-title {
    font-weight: 500;
    font-size: 20px;
    line-height: 24px;
    letter-spacing: 0px;
    text-align: right;
    vertical-align: middle;

}

.mobile-menu-list {
    display: flex;
    flex-direction: column;
    padding: 10px 0;
}

.mobile-menu-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 10px;
    padding: 15px 16px;
    text-decoration: none;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0px;
    text-align: right;
    vertical-align: middle;
    border-bottom: 1px solid #f0f0f0;
}

.arrow-icon {
    font-size: 14px;
}

.mobile-menu-footer {
    margin-top: 0px;
    background-color: #ECECEC4D;
    padding-bottom: 20px;
}

.mobile-footer-item {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    gap: 12px;
    padding: 15px 20px;
    text-decoration: none;
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    letter-spacing: 0px;
    text-align: right;
    vertical-align: middle;

    border-bottom: 1px solid #eee;
}

.mobile-footer-item.logout {
    color: #333;
}

.mobile-menu-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 999;
}


@media (max-width: 768px) {
    .header-top-bar {
        padding: 0 16px;
        height: 32px;
    }

    .header-top-mid-container {
        display: none;
    }

    .header-phone-number {
        display: none;
    }

    .header-main-container {
        height: 56px;
        padding: 0 16px;
    }

    .header-main-left-container {
        display: flex;
        align-items: center;
    }

    .header-main-right-container {
        display: none;
    }

    .header-logo {
        height: 24px;
    }

    .header-main-right-container-mobile {
        display: flex;
        align-items: center;
        gap: 20px;
    }

    .header-nav-menu {
        display: none;
    }
}
</style>