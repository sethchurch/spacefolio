<template>
  <main>
    <AboutSection />
  </main>
</template>

<script>
export default {
  name: 'AboutPage',
  head: {
    title: 'Seth Church | About Me',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Welcome to the about me page! Here\'s a list of my skills, including a variety of Web and Native technologies.'
      }
    ],
  }
}
</script>

<style lang="scss" scoped>

  main {
    display: flex;
    align-items: center;
    justify-content: space-between;
    min-height: 100vh;
  }

</style>