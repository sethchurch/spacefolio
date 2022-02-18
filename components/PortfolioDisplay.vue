<template>
    <div class="portfolio-display">

        <div class="portfolio-display__wrapper">
            <div class="portfolio-display__header">
                <h3  class="portfolio-display__title">{{ title }}</h3>

                <div class="portfolio-display__skills">
                    <span class="portfolio-display__skill-pill" v-for="skill in skills">{{ skill }}</span>
                </div>

            </div>
            <p class="portfolio-display__desc">{{ desc }}</p>

            <a target="_blank" :href="gitLink"><button class="portfolio-display__btn btn--orange btn--rounded">View Repo</button></a>
        </div>

        <div class="portfolio-display__img-wrapper">
            <img :src="imgSrc" :alt="imgAlt" class="portfolio-display__img" />
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
        background: #1f2329;
        display: flex;
        padding: 3rem 2rem;
        justify-content: space-between;
        gap: 2rem;
        align-items: stretch;

        &__header {
            display: flex;
            gap: 1rem;
        }

        &__wrapper {
            display: flex;
            flex-direction: column;
        }
        
        &__img-wrapper {
            height: 100%;
            flex: 30%;
            border-radius: 0.25rem;
            overflow: hidden;
            flex-shrink: 0;
            flex-grow: 0;
            max-height: 6rem;
            max-width: 9rem
        }

        &__title {
            color: $orange;
            font-size: 2em;
            font-weight: 700;
            margin: 0;
        }

        &__desc {
            font-size: 0.9em;
            margin-bottom: 1.25em;
        }

        &__img {
            max-width: 100%;
        }
        
        &__skill-pill {
            padding: 0.25em 1em;
            border: 3px $darkBlue solid;
            border-radius: 100em;
            font-size: 1em;
        }

        &__skills {
            display: flex;
            gap: 0.5rem;
            align-self: flex-end;
            margin: 0;
        }

        &__btn {
            border: 0;
            padding: 0.5em 2em;
            font-size: 1em;
            align-self: flex-end;
        }
    }


    @media (max-width: 1000px) {

        .portfolio-display {

            &__header {
                flex-direction: column;
            }

            &__skills {
                align-self: flex-start;
            }
        }

    }

    @media (max-width: 700px) {

        .portfolio-display {
            flex-direction: column-reverse;
            justify-content: flex-end;
            align-items: center;
            text-align: center;
            width: 100%;
            font-size: 0.9rem;
            gap: 1em;

            &__title {
                font-size: 1.5em;
            }

            &__img-wrapper {
                max-height: 10rem;
                max-width: 100%;
            }

            &__skills {
                margin: 0 auto;
                flex-wrap: wrap;
                justify-content: center;
            }

            &__skill-pill {
                padding: 0.25em 1em;
                border: 3px $darkBlue solid;
                border-radius: 100em;
                font-size: 0.9em;
            }
        }

    }
</style>