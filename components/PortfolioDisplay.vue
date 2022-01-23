<template>
    <div class="portfolio-display" :class="flip ? 'portfolio-display--flip' : ''">

        <div class="portfolio-display__head-wrapper" :class="planet ? 'portfolio-display__head-wrapper--planet' : 'portfolio-display__head-wrapper--square'">
            <div class="portfolio-display__container">
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
        imgAlt: String,
        flip: Boolean,
        planet: Boolean
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
        gap: 3rem;

        &--flip {
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

        &__container { 
            width: 12rem;
            height: 12rem;
            border-radius: 100%;
            position: relative;
            flex-shrink: 0;
            overflow: hidden;
            margin: 0;
            padding: 0;
            z-index: 0;
            &:after {
                content: ' ';
                position: absolute;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                border-radius: 100%;
                background: $blue;
                opacity: 0.1;
                transition: opacity 0.5s ease;
            }
            
        }

        &__head-wrapper {
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
            &--square {

                 & .portfolio-display__container {
                    top: 0;
                    border-radius: 1rem;
                    height: 18rem;
                    background: 0;
                    &:after { 
                        border-radius: 1rem;
                        opacity: 0.1;
                        // display: none; 
                    }
                }
            }

            &--planet {
                width: 18rem;
                height: 18rem;

                &:before {
                    content: ' ';
                    position: absolute;
                    width: 100%;
                    height: 100%;
                    background-image: url('~/assets/images/planet_ring.svg');
                    transition: all 40000ms ease-out;
                }
            }

            &:hover {
                & .portfolio-display__img {
                    width: 150%;
                }

                & .portfolio-display__container:after {
                    opacity: 0.35;
                }

                & .portfolio-display__view-btn {
                    opacity: 1;
                    transform: translateX(-50%) translateY(-50%) scale(1);
                }

                &:before {
                    transform: rotate(3600deg);
                }
            }
        }

        &__view-btn {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translateX(-50%) translateY(-50%) scale(0.5);
            text-align: center;
            height: 5rem;
            width: 5rem;
            border-radius: 100%;
            border: 0;
            opacity: 0;
            transition: all 0.5s ease;
        }

        &__skill-pill {
            padding: 0.25rem 1rem;
            border: 3px $darkBlue solid;
            border-radius: 100rem;
        }

        &__img {
            border: 0;
            width: 100%;
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            transition: all 0.5s ease;
            z-index: -1;
        }

        &__btn {
            border: 0;
            padding: 0.5rem 2rem;
            font-size: 1rem;
        }
        
    }
</style>