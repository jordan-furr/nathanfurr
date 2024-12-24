<template>
    <div class="ph3 header-cont w-100 borderbox">
        <div class="flex-row space-between block border-box align-center">
            <!--Logo-->
            <div class="">
                <a href="/" class="logo" exact-active-class="active">Nathan R. Furr</a>
            </div>
            <!--Desktop Nav-->
            <div class="flex-grow-1 flex-shrink-0 block desktop-nav">
                <div class="flex-row float-right">
                    <div class="block  borderbox pr5">
                        <div class="header-nav-list">
                            <div class="block">
                                <a href="/about" class="menu-item" exact-active-class="active">About</a>
                            </div>
                            <div class="block">
                                <a href="/booking" class="menu-item" exact-active-class="active">Booking</a>
                            </div>
                            <div class="block">
                                <a href="/publications" class="menu-item" exact-active-class="active">Publications</a>
                            </div>
                        </div>
                    </div>
                    <!--Socials-->
                    <div class="flex-row socials align-center">
                        <a href="https://fr.linkedin.com/in/nathan-furr-044852"><img
                                src=" /img/linkedin.png" class="social" alt=""></a>
                    </div>
                </div>
            </div>
            <!--Mobile Nav-->
            <div class="flex-grow-0 flex-shrink-1">
                <div class="mobile-menu">
                    <menu-icon :isOpen="isMenuVisible" @toggle-menu="toggleMenu" />
                    <mobile-menu :isVisible="isMenuVisible" @toggle-menu="toggleMenu" />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import mobileMenu from './mobile-menu.vue';
import menuIcon from './menu-icon.vue';
export default {
    components: { mobileMenu, menuIcon },
    data() {
        return {
            isMenuVisible: false
        }
    },
    methods: {
        toggleMenu() {
            this.isMenuVisible = !this.isMenuVisible;
        }
    }
}
</script>