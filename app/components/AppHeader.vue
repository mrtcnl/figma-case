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
                <span>
                    Watsons Beauty and Personal Care Awards Nominees!
                </span>
            </div>
            <div class="header-top-right-container">
                <div class="header-top-button">
                    <span>Call us:(+90) 850 123 45 67</span>
                    <Icon name="fa7-solid:phone-alt" size="20" />
                </div>
            </div>
        </div>

        <div class="header-main-container">
            <div class="header-main-left-container">
                <img class="header-logo" src="../assets/images/watsons-logo.png" alt="">
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

                        <img src="../assets/images/user-img.jpg" alt="Clara Clara" class="user-avatar" />

                        <Icon name="fa-solid:chevron-down" class="dropdown-icon" size="12" />
                    </div>

                    <div class="divider"></div>
                    <div class="cart-wrapper">
                        <Icon name="fa7-solid:basket-shopping" class="cart-icon" size="24" />
                        <span class="cart-badge">2</span>
                    </div>
                </div>
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
    </header>
</template>