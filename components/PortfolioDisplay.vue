<template>
    <div class="portfolio-display" :style="{ 'background-image': 'url(' + imgSrc + ')' }">

        <img :src="imgSrc" :alt="imgAlt" class="portfolio-display__img" />


        <div class="portfolio-display__wrapper">
            <h3  class="portfolio-display__title">{{ title }}</h3>

            <div class="portfolio-display__skills">
                <span class="portfolio-display__skill-pill" v-for="skill in skills">{{ skill }}</span>
            </div>

            <p class="portfolio-display__desc">{{ desc }}</p>

            <a target="_blank" :href="gitLink"><button class="portfolio-display__btn btn--orange btn--rounded">Learn More</button></a>
        </div>

    </div>
</template>

<script>
export default {
    props: {
        title: String,
        desc: String,
        skills: Array,
        gitLink: String,
        imgSrc: String,
        imgAlt: String
    }
}
</script>

<style lang="scss" scoped>
    @import '~/assets/css/variables';
    @import '~/assets/css/keyframes';

    .portfolio-display {
        display: flex;
        justify-self: center;
        align-items: center;
        gap: 3em;
        position: relative;
        background-size: cover;
        background-position: center;
        font-size: inherit;
        
        &__img {
            width: 100%;
            z-index: -1;
            display: block;
        }

        &__title {
            color: $orange;
            font-size: 1.5em;
            font-weight: 700;
        }

        &__desc {
            font-size: 0.9em;
            margin-bottom: 1.25em;
        }

        &__wrapper {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            background: adjust-color($color: $blue, $alpha: -0.95);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            transition: background 0.5s ease;
            padding: 1em;
            & > * {
                opacity: 0;
                transition: opacity 0.5s ease;
            }
            &:hover {
                background: adjust-color($color: $darkBlue, $alpha: -0.15);
                & > * {
                    opacity: 1;
                }
            }
        }

        &__skill-pill {
            padding: 0 0.3em;
            font-size: 0.95em;
            &:not(:last-child) {
                border-right: 0.15em solid $orange;
            }
        }

        &__btn {
            border: 0;
            padding: 0.5em 2em;
            font-size: 1em;
        }
    }
</style>