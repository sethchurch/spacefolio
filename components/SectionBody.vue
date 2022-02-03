<template>
    <article class="section-body">
        <h2 class="section-body__title text--orange">{{ title }}</h2>
        <div class="section-body__slot">
            <slot />
        </div>
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