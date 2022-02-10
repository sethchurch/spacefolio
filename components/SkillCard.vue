<template>
    <li class="skill-card">
        <div class="skill-card__inner">
            <div class="skill-card__front">
                <i class="about__skills-icon" :class="icon" />
            </div>
            <div class="skill-card__back">
                <p>{{ name }}</p>
            </div>
        </div>
    </li>
</template>

<style lang="scss" scoped>
    @import '~/assets/css/variables';

    .skill-card {
        display: flex;

        &--loading .skill-card__inner {
            transform: rotateY(180deg);
        }

        &__inner {
            position: relative;
            transition: transform 1s cubic-bezier(.54,.14,.16,1.32);
            background: lighten($baseBG, 10%);
            transform-style: preserve-3d;
            height: 7em;
            width: 7em;
            border-radius: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
        }
        
        &:hover .skill-card__inner {
            transform: rotateY(180deg);
            transition: transform 0.5s;
        }

        & .skill-card__front, .skill-card__back {
            height: 100%;
            width: 100%;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            backface-visibility: hidden;
        }
        
        &__front {
            font-size: 3rem;
        }

        &__back {
            top: 0;
            left: 0;
            position: absolute;
            font-size: 1.25rem;
            border-radius: 100%;
            transform: rotateY(180deg);
            background: $blue;
        }
    }

</style>

<script>
export default {
    props: {
        icon: String,
        name: String
    }
}
</script>