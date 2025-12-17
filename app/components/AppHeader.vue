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
                <a href="/" class="header-logo"><img class="header-logo" src="../assets/images/watsons-logo.png"
                        alt=""></a>
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
                    <a href="/checkout">
                        <div class="cart-wrapper">
                            <Icon name="fa7-solid:basket-shopping" class="cart-icon" size="24" />
                            <span class="cart-badge">2</span>
                        </div>
                    </a>
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
</style>