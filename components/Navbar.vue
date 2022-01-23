<template>
    <nav class="nav">
        <a href="/" class="nav__logo">
            <img src="portfolio_logo.svg">
        </a>

        <div class="nav__link-wrapper">
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
    </nav>
</template>

<style lang="scss" scoped>
    @import '~/assets/css/nav';
</style>