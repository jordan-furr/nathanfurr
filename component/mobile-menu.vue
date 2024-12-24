<template>
    <div class="menu-overlay" v-if="isVisible" @click="toggleMenu">
        <a href="/" class="logo" exact-active-class="active">Nathan R. Furr</a>
        <nav @click.stop>
            <ul>
                <li>
                    <nuxt-link to="/about" class="menu-item" @click="closeMenu" exact-active-class="active">
                        <p>About</p>
                    </nuxt-link>
                </li>
                <li>
                    <nuxt-link to="/booking" class="menu-item" @click="closeMenu" exact-active-class="active">
                        <p>Booking</p>
                    </nuxt-link>
                </li>
                <li>
                    <nuxt-link to="/publications" class="menu-item" @click="closeMenu" exact-active-class="active">
                        <p>Publications</p>
                    </nuxt-link>
                </li>
            </ul>
            <div class="socials flex-row align-center">
                <a href="https://fr.linkedin.com/in/nathan-furr-044852"><img src=" /img/linkedin.png" class="social"
                        alt=""></a>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    props: {
        isVisible: {
            type: Boolean,
            required: true
        }
    },
    methods: {
        toggleMenu() {
            this.$emit('toggle-menu');
        },
        closeMenu() {
            this.$emit('toggle-menu');
        }
    }
}
</script>