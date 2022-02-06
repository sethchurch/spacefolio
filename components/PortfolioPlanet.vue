<template>
    <div class="portfolio-planet">

        <div class="portfolio-planet__head-wrapper portfolio-planet__head-wrapper--planet">
            <div class="portfolio-planet__container">
                <img :src="imgSrc" :alt="imgAlt" class="portfolio-planet__img" />
            </div>
            <a target="_blank" :href="gitLink"><button class="portfolio-planet__view-btn btn--blue" >View Project</button></a>
        </div>

        <div class="portfolio-planet__wrapper">
            <h3  class="portfolio-planet__title">{{ title }}</h3>

            <div class="portfolio-planet__skills">
                <span class="portfolio-planet__skill-pill" v-for="skill in skills">{{ skill }}</span>
            </div>

            <p class="portfolio-planet__desc">{{ desc }}</p>

            <a target="_blank" :href="gitLink"><button class="portfolio-planet__btn btn--blue btn--rounded">View Project</button></a>
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
    },
    methods: {
        addAnimationObserver() {
            const observer = new IntersectionObserver(entries => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('portfolio-planet--animated');
                    }
                });
            });

            observer.observe(this.$el);
        }
    },
    mounted: function() {
        this.addAnimationObserver();
    }
}
</script>

<style lang="scss" scoped>
    @import '~/assets/css/variables';
    @import '~/assets/css/keyframes';

    .portfolio-planet {
        display: flex;
        justify-self: center;
        align-items: center;
        gap: 3em;

        // Animation Class Rules
        &--animated {
            &:nth-child(2n - 1) {
                .portfolio-planet__wrapper {
                    animation-name: fade-enter-right;
                }
            }

            .portfolio-planet {
                &__head-wrapper {
                    animation-name: scale-in;
                    animation-timing-function: cubic-bezier(.54,.14,.16,1.32);
                    animation-duration: 0.5s;
                    animation-iteration-count: 1;
                }
                &__wrapper {
                    animation-name: fade-enter-left;
                    animation-timing-function: ease;
                    animation-fill-mode: forwards;
                    animation-duration: 1s;
                    animation-iteration-count: 1;
                    animation-delay: 0.55s;
                }

            }
        }

        &:nth-child(2n - 1) {
            text-align: right;
            flex-direction: row-reverse;
            .portfolio-planet {
                &__wrapper {
                    display: flex;
                    flex-direction: column;
                    align-items: flex-end;
                    text-align: inherit;
                }
                &__title {
                    &:after {
                        right: 0.1em;
                    }
                }
            }
        }
        
        &__title {
            font-size: 2em;
            margin: 0 0 1.25em 0;
            &:after {
                position: absolute;
                content: ' ';
                display: block;
                height: 0.2em;
                width: 3em;
                background: $orange;
                margin: 0.5em 0;
            }
        }

        &__container { 
            width: 12em;
            height: 12em;
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

        &__wrapper {
            position: relative;

            right: 10%;
            opacity: 0;
        }

        &__head-wrapper {
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;

            &--planet {
                width: 18em;
                height: 18em;

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
                & .portfolio-planet__img {
                    width: 150%;
                }

                & .portfolio-planet__container:after {
                    opacity: 0.35;
                }

                & .portfolio-planet__view-btn {
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
            height: 5em;
            width: 5em;
            border-radius: 100%;
            border: 0;
            opacity: 0;
            transition: all 0.5s ease;
        }

        &__skills {
            display: flex;
            gap: 0 0.5em; 
        }

        &__skill-pill {
            padding: 0.25em 1em;
            border: 3px $darkBlue solid;
            border-radius: 100em;
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
            padding: 0.5em 2em;
            font-size: 1em;
        }
        
    }

    @media (max-width: 1000px) {
        .portfolio-planet {
            flex-direction: column;
            text-align: center;
            justify-content: center;
            align-items: center;
            margin-bottom: 3em;
            gap: 1rem;
            font-size: inherit;

            &--animated {
                .portfolio-planet {
                    &__wrapper {
                        left: 0;
                        animation-name: fade-enter-up !important;
                        animation-duration: 0.75s;
                    }

                }
            }

            &:nth-child(2n - 1) {
                text-align: center;
                flex-direction: column;
                width: 100%;
                .portfolio-planet {
                    &__wrapper {
                        align-items: center;
                    }
                }
            }

            &__title {
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                &:after {
                    position: relative;
                    margin-bottom: 0;
                }
            }

            &__skills {
                justify-content: center;
            }
        }
    }

    @media (max-width: 1000px) {
        .portfolio-planet {
            &__title {
                margin: 1rem 0.5rem;
                &:after {
                    height: 0.2em;
                }
            }
            &__skill-pill {
                font-size: 0.9rem;
            }
        }
    }
</style>