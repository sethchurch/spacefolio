<template>
    <nav class="nav">
        <nuxt-link to="/" class="nav__logo">
            <img src="portfolio_logo.svg">
        </nuxt-link>

        <div class="nav__link-wrapper">
            <nuxt-link class="nav__link" to="/"><div><fa icon="home" /></div></nuxt-link>
            <nuxt-link class="nav__link" to="/about"><div><fa icon="cog" /></div></nuxt-link>
            <nuxt-link class="nav__link" to="/skills"><div><fa icon="cog" /></div></nuxt-link>
            <nuxt-link class="nav__link" to="/work"><div><fa icon="cog" /></div></nuxt-link>
            <nuxt-link class="nav__link" to="/contact"><div><fa icon="cog" /></div></nuxt-link>
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