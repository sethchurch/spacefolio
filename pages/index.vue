<template>
  <section class="landing">
    <header class="landing__header">
      <h1 class="landing__header-text">Hey, <br>I'm Seth<span class="text--orange">.</span></h1>
      <h2 class="landing__subheader text--blue">Software Engineer</h2>
      <a class="landing__link" href="/contact"><button class="landing__btn btn--orange btn--rounded">Contact Me!</button></a>
    </header>
  </section>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style lang="scss" scoped>
  @import '~/assets/css/landing';
</style>