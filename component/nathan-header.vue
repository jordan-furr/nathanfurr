<template>
    <div class="ph3 header-cont w-100 borderbox" :hidden="isHidden">
        <div class="flex-row space-between block border-box align-center">
            <!--Logo-->
            <div class="">
                <a href="/" class="logo" exact-active-class="active">Nathan Furr</a>
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
                    <div class="flex-grow-0 flex-shrink-1">
                        <a href="/" class="menu-item" exact-active-class="active">in</a>
                    </div>
                </div>
            </div>
            <!--Burger-->
            <div class="flex-grow-0 flex-shrink-1 burger-menu">
                <div class="burger" @click="toggleMenu">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </div>
            <!--Mobile Nav-->
            <transition name="slide-right">
                <div v-if="menuOpen" class="mobile-nav">
                    <a href="/about" class="menu-item" exact-active-class="active">About</a>
                    <a href="/booking" class="menu-item" exact-active-class="active">Booking</a>
                    <a href="/publications" class="menu-item" exact-active-class="active">Publications</a>
                </div>
            </transition>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            menuOpen: false,
            isHidden: false,
            lastScrollY: 0
        };
    },
    methods: {
        toggleMenu() {
            this.menuOpen = !this.menuOpen;
        },
        handleScroll() {
            const currentScrollY = window.scrollY;
            this.isHidden = currentScrollY > this.lastScrollY;
            this.lastScrollY = currentScrollY;
        }
    },
    mounted() {
        this.lastScrollY = window.scrollY;
        window.addEventListener("scroll", this.handleScroll);
    },
    beforeDestroy() {
        window.removeEventListener("scroll", this.handleScroll);
    }
};
</script>
