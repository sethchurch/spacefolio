<template>
    <nav class="nav">
        <a href="/" class="nav__logo" v-on:click="toggleMobileNav($event)">
            <img src="/portfolio_logo.svg" alt="Seth's Logo">
        </a>

        <div class="nav__link-wrapper" v-on:click="toggleMobileNav($event)">
            <nuxt-link class="nav__link" to="/"><p>Home</p></nuxt-link>
            <nuxt-link class="nav__link" to="/about"><p>About Me</p></nuxt-link>
            <!-- <nuxt-link class="nav__link" to="/skills"><p>My Skills</p></nuxt-link> -->
            <nuxt-link class="nav__link" to="/work"><p>My Work</p></nuxt-link>
            <nuxt-link class="nav__link" to="/contact"><p>Contact</p></nuxt-link>
        </div>

        <div class="nav__social-links">
            <a target="_blank" href="https://www.linkedin.com/in/gschurch/">
                <fa :icon="['fab', 'linkedin-in']" />
            </a>

            <a target="_blank" href="https://github.com/iEnder">
                <fa :icon="['fab', 'github']" />
            </a>

            <a target="_blank" href="https://codepen.io/pkmn9060/">
                <fa :icon="['fab', 'codepen']" />
            </a>
        </div>

        <div id="mobileNavBtn" class="nav__mobile-link" v-on:click="toggleMobileNav($event)">
            <fa class="nav__mobile-link--open" :icon="['fa', 'bars']" />
            <!-- <fa class="nav__mobile-link--close" :icon="['fa', 'bars']" /> -->
        </div>
    </nav>
</template>

<style lang="scss" scoped>
    @import '~/assets/css/nav';
</style>


<script>
    export default {
        methods: {
            toggleMobileNav: () => {
                document.querySelector('.nav').classList.toggle('nav--active');
            }
        }
    }
</script>