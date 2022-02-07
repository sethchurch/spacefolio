<template>
    <div class="section-body">
        <h2 class="section-body__title text--orange">{{ title }}</h2>
        <div class="section-body__slot">
            <slot />
        </div>
    </div>
</template>

<script>
export default {
    props: ['title'],
    methods: {
        addAnimationObserver() {
            const observer = new IntersectionObserver(entries => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('section-body--animated');
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
    @import '~/assets/css/layout';
</style>