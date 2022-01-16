<template>
    <div class="work-display">
        <!-- <img class="work-display__img" src="https://source.unsplash.com/random/?web" alt="work image"> -->
    </div>
</template>

<style lang="scss" scoped>
    .work-display {
        overflow: hidden;
        position: relative;
        background-image: url('https://source.unsplash.com/random/?web');
        background-size: cover;
        &__img {
            display: block;
            width: 100%;
        }
    }
</style>