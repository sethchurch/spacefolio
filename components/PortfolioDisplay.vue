<template>
    <div class="portfolio-display">

        <div class="portfolio-display__ring">
            <div class="portfolio-display__planet">
                <img :src="imgSrc" :alt="imgAlt" class="portfolio-display__img" />
            </div>
            <button class="portfolio-display__view-btn btn--blue" >View Project</button>
        </div>

        <div class="portfolio-display__wrapper">
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
        gap: 3rem;

        &:nth-child(2n+1) {
            flex-direction: row-reverse;
            .portfolio-display {
                &__wrapper {
                    display: flex;
                    flex-direction: column;
                    align-items: flex-end;
                    text-align: right;
                }
                &__title {
                    &:after {
                        margin-left: calc(100% - 4rem);
                    }
                }
            }
        }
        
        &__title {
            font-size: 2rem;
            margin: 1rem 0;
            &:after {
                content: ' ';
                display: block;
                height: 0.4rem;
                width: 4rem;
                background: $orange;
                margin: 0.5rem 0;
            }
        }

        &__planet { 
            width: 10rem;
            height: 10rem;
            background: $blue;
            // border: 5px #163E66 solid;
            border-radius: 100%;
            position: relative;
            flex-shrink: 0;
            overflow: hidden;
            margin: 0;
            padding: 0;
            opacity: 0.6;
        }

        &__ring {
            width: 15rem;
            height: 15rem;
            // background: $blue;
            border: 5px #163E66 solid;
            border-radius: 100%;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
            &:hover .portfolio-display__view-btn {
                display: block;
            }
        }

        &__view-btn {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translateX(-50%) translateY(-50%);
            text-align: center;
            height: 5rem;
            width: 5rem;
            border-radius: 100%;
            border: 0;
            display: none;
        }

        &__skill-pill {
            padding: 0.25rem 1rem;
            border: 3px $darkBlue solid;
            border-radius: 100rem;
        }

        &__img {
            border: 0;
            width: 100%;
            position: relative;
            z-index: -1;
        }

        &__btn {
            border: 0;
            padding: 0.5rem 2rem;
            font-size: 1rem;
        }
        
    }
</style>