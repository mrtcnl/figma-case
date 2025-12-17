<template>
    <div class="footer-container">
        <div class="footer-top-container">

            <div class="footer-list-container">
                <div class="footer-title-wrapper" @click="toggleAccordion('corporate')">
                    <h3 class="footer-title">CORPORATE</h3>
                    <Icon name="fa-solid:chevron-down" class="accordion-icon"
                        :class="{ 'rotate': activeSection === 'corporate' }" />
                </div>
                <div class="footer-links" :class="{ 'mobile-hidden': activeSection !== 'corporate' }">
                    <a href="#" class="footer-link-item">About us</a>
                    <a href="#" class="footer-link-item">Press</a>
                    <a href="#" class="footer-link-item">Human resources</a>
                    <a href="#" class="footer-link-item">News from us</a>
                </div>
            </div>

            <div class="footer-list-container">
                <div class="footer-title-wrapper" @click="toggleAccordion('shopping')">
                    <h3 class="footer-title">SHOPPING</h3>
                    <Icon name="fa-solid:chevron-down" class="accordion-icon"
                        :class="{ 'rotate': activeSection === 'shopping' }" />
                </div>
                <div class="footer-links" :class="{ 'mobile-hidden': activeSection !== 'shopping' }">
                    <a href="#" class="footer-link-item">Order and Payment</a>
                    <a href="#" class="footer-link-item">Cancellation and Refund</a>
                    <a href="#" class="footer-link-item">Delivery Conditions</a>
                    <a href="#" class="footer-link-item">Secure shopping</a>
                </div>
            </div>

            <div class="footer-list-container">
                <div class="footer-title-wrapper" @click="toggleAccordion('legal')">
                    <h3 class="footer-title">LEGAL</h3>
                    <Icon name="fa-solid:chevron-down" class="accordion-icon"
                        :class="{ 'rotate': activeSection === 'legal' }" />
                </div>
                <div class="footer-links" :class="{ 'mobile-hidden': activeSection !== 'legal' }">
                    <a href="#" class="footer-link-item">Terms of Use</a>
                    <a href="#" class="footer-link-item">Privacy Policy</a>
                    <a href="#" class="footer-link-item">Membership Agreement</a>
                    <a href="#" class="footer-link-item">Distance Selling Contract</a>
                </div>
            </div>

            <div class="footer-list-container">
                <div class="footer-title-wrapper" @click="toggleAccordion('help')">
                    <h3 class="footer-title">HELP CENTER</h3>
                    <Icon name="fa-solid:chevron-down" class="accordion-icon"
                        :class="{ 'rotate': activeSection === 'help' }" />
                </div>
                <div class="footer-links" :class="{ 'mobile-hidden': activeSection !== 'help' }">
                    <a href="#" class="footer-link-item">FAQ</a>
                    <a href="#" class="footer-link-item">Contact center</a>
                </div>
            </div>

            <div class="footer-list-container footer-contact-container">
                <div class="footer-title-wrapper" @click="toggleAccordion('contact')">
                    <h3 class="footer-title">CONTACT US</h3>
                    <Icon name="fa-solid:chevron-down" class="accordion-icon"
                        :class="{ 'rotate': activeSection === 'contact' }" />
                </div>
                <div class="footer-links" :class="{ 'mobile-hidden': activeSection !== 'contact' }">
                    <div class="contact-item">
                        <Icon name="fa-solid:map-marker-alt" size="14" class="contact-icon" />
                        <span>Saray Mah. Site Yolu Cad. Anel İş Merkezi, D:No:5/4, 34768 Ümraniye/İstanbul</span>
                    </div>
                    <div class="contact-item">
                        <Icon name="fa-solid:phone-alt" size="14" class="contact-icon" />
                        <span>0850 755 9987</span>
                    </div>
                    <div class="contact-item">
                        <Icon name="fa-solid:envelope" size="14" class="contact-icon" />
                        <span>info@watsons.com.tr</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="footer-bottom-container">
            <span class="copyright-text">
                © WATSONS 2021 ALL RIGHTS RESERVED | A MEMBER OF CK HUTCHISON HOLDINGS
            </span>

            <div class="social-icons">
                <a href="#">
                    <Icon name="fa-brands:facebook" class="social-icon fb" />
                </a>
                <a href="#">
                    <Icon name="fa-brands:twitter" class="social-icon tw" />
                </a>
                <a href="#">
                    <Icon name="fa-brands:instagram" class="social-icon ig" />
                </a>
                <a href="#">
                    <Icon name="fa-brands:youtube" class="social-icon yt" />
                </a>
                <a href="#">
                    <Icon name="fa-brands:pinterest" class="social-icon pin" />
                </a>
            </div>
        </div>

    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const activeSection = ref<string | null>(null)

const toggleAccordion = (section: string) => {
    if (activeSection.value === section) {
        activeSection.value = null
    } else {
        activeSection.value = section
    }
}
</script>

<style scoped>
.footer-container {
    width: 100%;
    padding: 48px 140px;
    background-color: #fff;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 32px;
}

.footer-top-container {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 20px;
    width: 100%;
}

.footer-list-container {
    display: flex;
    flex-direction: column;
    gap: 32px;
}

.footer-contact-container {
    max-width: 250px;
}

.footer-title {
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    text-transform: uppercase;
    color: #2A2A48;
    margin: 0;
}

.footer-title-wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: default;
}

.accordion-icon {
    display: none;
    color: #2A2A48;
    font-size: 14px;
    transition: transform 0.3s ease;
}

.accordion-icon.rotate {
    transform: rotate(180deg);
}

.footer-links {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.footer-link-item {
    font-weight: 400;
    font-size: 12px;
    line-height: 16px;
    text-decoration: none;
    color: #485363;
}

.footer-link-item:hover {
    text-decoration: underline;
    color: #0099A8;
}

.contact-item {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 12px;
    color: #485363;
    line-height: 1.5;
}

.contact-icon {
    color: #485363;
    margin-top: 2px;
    min-width: 14px;
}

.footer-bottom-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 10px;
}

.copyright-text {
    font-weight: 500;
    font-size: 10px;
    line-height: 16px;
    letter-spacing: 0px;
    vertical-align: middle;
    text-transform: uppercase;
    color: #8493A8;
}

.social-icons {
    display: flex;
    gap: 12px;
}

.social-icon {
    font-size: 28px;
    cursor: pointer;
    transition: transform 0.2s;
}

.fb {
    color: #3b5998;
}

.tw {
    color: #1da1f2;
}

.ig {
    color: #e1306c;
}

.yt {
    color: #ff0000;
}

.pin {
    color: #bd081c;
}

.social-icon:hover {
    transform: scale(1.1);
}

@media (max-width: 768px) {
    .footer-container {
        padding: 0;
        gap: 0;
    }

    .footer-top-container {
        flex-direction: column;
        gap: 0;
    }

    .footer-list-container {
        width: 100%;
        gap: 0;
        border-bottom: 1px solid #EAEAEA;
    }

    .footer-contact-container {
        max-width: 100%;
    }

    .footer-title-wrapper {
        padding: 20px;
        cursor: pointer;
        background-color: #fff;
    }

    .accordion-icon {
        display: block;
    }

    .footer-links {
        padding: 0 20px 20px 20px;
        gap: 16px;
        transition: all 0.3s ease-in-out;
    }

    .mobile-hidden {
        display: none;
    }

    .footer-bottom-container {
        flex-direction: column-reverse;
        gap: 20px;
        padding: 30px 20px;
        text-align: center;
    }

    .copyright-text {
        width: 60%;
        font-weight: 500;
        font-size: 10px;
        line-height: 16px;
        letter-spacing: 0px;
        vertical-align: middle;
        text-transform: uppercase;
        color: #8493A8;
    }
}
</style>