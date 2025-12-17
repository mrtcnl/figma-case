<template>
    <div class="checkout-page-container">
        <div class="checkout-page-header">
            <div class="checkout-page-header-links">
                <a href="#" class="checkout-page-header-link">Homepage</a>
                <span class="checkout-page-header-separator">></span>
                <a href="#" class="checkout-page-header-link">Shopping Cart</a>
                <span class="checkout-page-header-separator">></span>
                <a href="#" class="checkout-page-header-link active">Checkout</a>
            </div>
            <h1 class="checkout-page-header-title">Checkout</h1>
        </div>

        <div class="checkout-page-main-content">

            <div class="checkout-page-left-container">
                <div class="form-section">
                    <h2 class="section-title">
                        <Icon name="fa-solid:shipping-fast" size="20" class="section-icon" />
                        Shipping details
                    </h2>
                    <div class="form-grid">
                        <div class="form-group"><label>First Name *</label><input type="text" class="form-input" />
                        </div>
                        <div class="form-group"><label>Last Name *</label><input type="text" class="form-input" /></div>
                        <div class="form-group"><label>Email Address *</label><input type="email" class="form-input" />
                        </div>
                        <div class="form-group"><label>Phone Number *</label><input type="text" class="form-input"
                                placeholder="+90 (5__) ___ __ __" /></div>
                        <div class="form-group"><label>City *</label>
                            <div class="select-wrapper">
                                <select class="form-input">
                                    <option>Please select</option>
                                    <option>İstanbul</option>
                                    <option>Ankara</option>
                                </select>
                            </div>
                        </div>
                        <div class="form-group"><label>District *</label>
                            <div class="select-wrapper">
                                <select class="form-input">
                                    <option>Please select</option>
                                </select>
                            </div>
                        </div>
                        <div class="form-group full-width"><label>Address *</label><textarea class="form-input textarea"
                                placeholder="Enter neighborhood, street, avenue and other information"></textarea></div>
                    </div>
                </div>

                <div class="form-section">
                    <h2 class="section-title">
                        <Icon name="fa-solid:money-check-alt" size="20" class="section-icon" />
                        Payment details
                    </h2>
                    <div class="payment-layout">
                        <div class="payment-form">
                            <div class="form-group full-width"><label>Card Holder Name *</label><input type="text"
                                    class="form-input" v-model="cardForm.holderName"
                                    @input="cardForm.holderName = cardForm.holderName.toUpperCase()" maxlength="26" />
                                <div class="required-note">Full name on card</div>
                            </div>
                            <div class="form-group full-width"><label>Card Number *</label>
                                <input type="text" class="form-input" v-model="cardForm.cardNumber"
                                    @input="formatCardNumber" placeholder="0000 0000 0000 0000" maxlength="19" />
                                <div class="required-note">Enter digits without spaces</div>
                            </div>
                            <div class="form-grid">
                                <div class="form-group"><label>Expiry Date *</label><input type="text"
                                        class="form-input" v-model="cardForm.expiryDate" placeholder="MM / YY"
                                        maxlength="5" @input="formatExpiryDate" /></div>
                                <div class="form-group"><label>CVV *</label>
                                    <div class="cvv-wrapper"><input type="text" class="form-input"
                                            v-model="cardForm.cvv" maxlength="3" />
                                        <Icon name="fa-solid:question-circle" class="cvv-icon" />
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="visual-card">
                            <div class="card-chip">
                                <Icon name="fa-solid:microchip" size="24" color="#EAB308" />
                            </div>
                            <div class="card-number">{{ cardForm.cardNumber || '0000 0000 0000 0000' }}</div>
                            <div class="card-details">
                                <div class="card-holder"><span>Card Holder</span><strong>
                                        {{ cardForm.holderName || 'CARD HOLDER' }}</strong>
                                </div>
                                <div class="card-cvv"><span>CVV</span><strong>{{ cardForm.cvv || 'XXX' }}</strong></div>
                                <div
                                    style="position: absolute; bottom: 20px; right: 20px; text-align: right; font-size: 12px; color: #666;">
                                    <span>Expires</span><br><strong style="color: #333; font-size: 14px; ">{{
                                        cardForm.expiryDate || 'MM / YY' }}</strong>
                                </div>
                            </div>

                        </div>
                    </div>
                </div>
                <div class="required-note">* Required fields</div>
                <button class="pay-btn">PAY NOW</button>
            </div>

            <div class="checkout-page-right-container">
                <h2 class="section-title">
                    Shopping cart summary
                </h2>
                <div class="cart-summary-box">

                    <div class="cart-items">
                        <div v-for="item in cartItems" :key="item.id" class="cart-item">
                            <div class="item-image">
                                <img :src="item.image" :alt="item.name" />
                            </div>
                            <div class="item-details">
                                <h3 class="item-name">{{ item.name }}</h3>
                                <div class="item-price-container">
                                    <div class="item-price">{{ item.price }} TL</div>

                                    <div class="qty-controls">
                                        <button class="qty-btn" @click="decreaseQty(item.id)">-</button>
                                        <span class="qty-value">{{ item.quantity }}</span>
                                        <button class="qty-btn" @click="increaseQty(item.id)">+</button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <input type="text" class="form-input" placeholder="Discount code" />
                    <div class="cart-totals">
                        <div class="total-row">
                            <span>Subtotal</span>
                            <span>{{ subTotal.toFixed(2) }} TL</span>
                        </div>
                        <div class="total-row">
                            <span>Shipping</span>
                            <span>{{ shippingCost }} TL</span>
                        </div>
                        <div class="divider"></div>
                        <div class="total-row grand-total">
                            <span>Total</span>
                            <span>{{ grandTotal.toFixed(2) }} TL</span>
                        </div>
                    </div>

                </div>
            </div>

        </div>
    </div>
</template>

<script setup lang="ts">
import { reactive, ref, computed } from 'vue'

import img1 from '../assets/images/featured-products/featured1.png'
import img2 from '../assets/images/featured-products/featured3.png'

useHead({
    title: 'Watsons - Checkout'
})

const cartItems = ref([
    {
        id: 1,
        name: 'Herbal Science Boom Butter Hair Care Oil 190 ml',
        price: 44.95,
        quantity: 1,
        image: img1
    },
    {
        id: 2,
        name: 'Diadermine Lift + Serum Booster Vitamin C',
        price: 29.45,
        quantity: 1,
        image: img2
    }
])


const shippingCost = 10.50

const subTotal = computed(() => {
    return cartItems.value.reduce((total, item) => total + (item.price * item.quantity), 0)
})

const grandTotal = computed(() => {
    return subTotal.value + shippingCost
})

const increaseQty = (id: number) => {
    const item = cartItems.value.find(i => i.id === id)
    if (item) item.quantity++
}

const decreaseQty = (id: number) => {
    const item = cartItems.value.find(i => i.id === id)
    if (item && item.quantity > 1) {
        item.quantity--
    }
}

const cardForm = reactive({
    holderName: '',
    cardNumber: '',
    expiryDate: '',
    cvv: ''
})

const formatCardNumber = (e: Event) => {
    const target = e.target as HTMLInputElement
    let value = target.value.replace(/\D/g, '')
    value = value.replace(/(\d{4})(?=\d)/g, '$1 ')
    cardForm.cardNumber = value
}

const formatExpiryDate = (e: Event) => {
    const target = e.target as HTMLInputElement
    let value = target.value.replace(/\D/g, '')
    if (value.length >= 2) {
        value = value.substring(0, 2) + '/' + value.substring(2, 4)
    }
    cardForm.expiryDate = value
}
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
    color: #999;
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
    display: flex;
    flex-direction: column;
    gap: 32px;
}

.checkout-page-right-container {
    grid-column: span 1 / span 1;
    display: flex;
    flex-direction: column;
    gap: 32px;
}

.form-section {
    display: flex;
    flex-direction: column;
    gap: 32px;
}

.section-title {
    font-weight: 500;
    font-size: 20px;
    line-height: 24px;
    letter-spacing: 0px;
    vertical-align: middle;
    color: #2A2A48;
    margin: 0;
}

.section-icon {
    color: #555;
    margin-right: 12px;
}

.form-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    column-gap: 40px;
    row-gap: 16px;
}

.form-group {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.full-width {
    grid-column: span 2;
}

.form-group label {
    font-weight: 400;
    font-size: 14px;
    line-height: 24px;
    letter-spacing: 0px;
    color: #2A2A48;
}

.form-input {
    border: 1px solid #ECECEC;
    border-radius: 4px;
    padding: 16px;
    font-size: 14px;
    color: #333;
    outline: none;
    width: 100%;
    height: 48px;
}

.form-input:focus {
    border-color: #0099A8;
}

.form-input.textarea {
    height: 123px;
    resize: none;
}

.select-wrapper {
    position: relative;
}

.form-input[type="select"] {
    appearance: none;
    background-color: white;
}

.select-icon {
    position: absolute;
    right: 12px;
    top: 50%;
    transform: translateY(-50%);
    color: #999;
    pointer-events: none;
    font-size: 12px;
}

.payment-layout {
    display: flex;
    gap: 30px;
    align-items: flex-start;
}

.payment-form {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.cvv-wrapper {
    position: relative;
}

.cvv-icon {
    position: absolute;
    right: 10px;
    top: 50%;
    transform: translateY(-50%);
    color: #999;
}

.visual-card {
    width: 40%;
    height: 200px;
    border: 1px solid #E0E0E0;
    border-radius: 12px;
    background: white;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
    position: relative;
}

.card-number {
    font-size: 18px;
    letter-spacing: 2px;
    color: #333;
    font-family: monospace;
}

.card-details {
    display: flex;
    justify-content: space-between;
    color: #666;
    font-size: 12px;
    padding-right: 60px;
}

.card-details strong {
    display: block;
    color: #333;
    font-size: 14px;
    margin-top: 4px;
}

.required-note {
    font-size: 12px;
    color: #8493A8;
    margin-top: 2px;
}

.pay-btn {
    background-color: #FF27AD;
    color: white;
    border: none;
    border-radius: 4px;
    font-weight: 700;
    font-size: 16px;
    cursor: pointer;
    margin-top: 20px;
    height: 32px;
    width: 50%;
}

.pay-btn:hover {
    background-color: #e61e9a;
}

.cart-summary-box {
    box-shadow: 0px 4px 16px 0px #2A2A480A;
    border: 1px solid #ECECEC;
    border-radius: 6px;
    padding: 24px;
    display: flex;
    flex-direction: column;
    gap: 24px;
}

.cart-title {
    font-size: 18px;
    font-weight: 500;
    color: #2A2A48;
    margin: 0;
    border-bottom: 1px solid #E0E0E0;
    padding-bottom: 12px;
}

.cart-items {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.cart-item {
    display: flex;
    gap: 16px;
    align-items: flex-start;
    box-shadow: 0px 1px 2px 0px #37415114;
}

.item-image {
    width: 40%;
    height: 100%;
    padding: 16px;
    border-radius: 4px;
    background-color: #ECECEC29;
    display: flex;
    align-items: center;
    justify-content: center;
}

.item-image img {
    max-width: 100%;
    max-height: 96px;
    object-fit: contain;
}

.item-details {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.item-name {
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    letter-spacing: 0px;
    vertical-align: middle;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
    color: #2A2A48;
}

.item-price-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.item-price {
    font-weight: 700;
    font-size: 14px;
    color: #0099A8;
}

.qty-controls {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 4px;
}

.qty-btn {
    width: 24px;
    height: 24px;
    border: 1px solid #ccc;
    background-color: white;
    color: #333;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 4px;
    font-size: 14px;
}

.qty-btn:hover {
    background-color: #eee;
    border-color: #bbb;
}

.qty-value {
    font-size: 14px;
    font-weight: 500;
    min-width: 20px;
    text-align: center;
}

.cart-totals {
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-top: 10px;
}

.total-row {
    display: flex;
    justify-content: space-between;
    font-size: 16px;
    font-weight: 400;
    color: #485363;
}

.divider {
    width: 100%;
    height: 1px;
    background-color: #ECECEC;
    margin: 8px 0;
}

.grand-total {
    font-size: 18px;
    font-weight: 700;
    color: #2A2A48;
}

@media (max-width: 768px) {
    .checkout-page-main-content {
        padding: 16px;
        grid-template-columns: 1fr;
    }

    .checkout-page-left-container {
        grid-column: span 1;
        gap: 16px;
    }

    .checkout-page-right-container {
        grid-column: span 1;
        order: -1;
        gap: 16px;
    }

    .payment-layout {
        flex-direction: column-reverse;
    }

    .visual-card {
        width: 100%;
        margin-bottom: 20px;
    }

    .checkout-page-header {
        padding: 16px;
    }

    .checkout-page-header-title {
        font-size: 24px;
        line-height: 32px;
    }

    .section-title {
        font-size: 20px;
        line-height: 24px;
        display: flex;
        align-items: center;
        gap: 16px;
    }

    .cart-summary-box {
        box-shadow: none;
        border: none;
        border-radius: 6px;
        padding: 0px;
        display: flex;
        flex-direction: column;
        gap: 16px;
    }

    .form-grid {
        display: flex;
        flex-direction: column;
        gap: 16px;
    }

    .payment-form {
        flex: 1;
        display: flex;
        width: 100%;
        flex-direction: column;
        gap: 20px;
    }

    .pay-btn {
        height: 32px;
        width: 100%;
    }
}
</style>