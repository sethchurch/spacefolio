<template>
    <article class="section-body">
        <h2 class="section-body__title text--orange">{{ title }}</h2>
        <p class="section-body__text">
            <slot />
        </p>
    </article>
</template>

<script>
export default {
    props: ['title']
}
</script>

<style lang="scss" scoped>
    @import '~/assets/css/layout';
</style>