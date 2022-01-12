<template>
    <div class="portfolio-display">

        <div class="portfolio-display__planet">
            <img :src="imgSrc" :alt="imgAlt" class="portfolio-display__img" />
            <p>View Project</p>
        </div>

        <div>
            <h3  class="portfolio-display__title">{{ title }}</h3>

            <div class="portfolio-display__skills">
                <span class="portfolio-display__skill-pill">Vue.JS</span>
                <span class="portfolio-display__skill-pill">SASS</span>
                <span class="portfolio-display__skill-pill">Javascript</span>
            </div>

            <p class="portfolio-display__desc">{{ desc }}</p>

            <a href="/"><button class="portfolio-display__btn btn--blue btn--rounded">Learn More</button></a>
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

    .portfolio-display {
        display: flex;
        justify-self: center;
        align-items: center;
        
        &__title {
            font-size: 2rem;
            margin: 1rem 0;
        }

        &__planet {
            width: 10rem;
            height: 10rem;
            background: $blue;
            border-radius: 100%;
            position: relative;
            flex-shrink: 0;
            margin-right: 1rem;
            p {
                position: absolute;
                top: 0;
                left: 0;
                text-align: center;
                height: 100%;
                width: 100%;
            }
        }

        &__skill-pill {
            padding: 0.25rem 1rem;
            border: 3px #163E66 solid;
            border-radius: 100rem;
        }

        &__img {
            border: 0;
            text-decoration: none;
        }

        &__btn {
            border: 0;
            padding: 0.5rem 2rem;
            font-size: 1rem;
        }
        
    }
</style>