<template>
  <main class="contact">
      <SectionBody title="Contact">
        <p>If you're looking to collaborate on a project, get in touch about a position, or say hi, feel free to use the form below. I'll be in touch with you as soon as I can.</p>
      </SectionBody>

      <ContactForm class="contact__form" />
  </main>
</template>

<script>
export default {
  name: 'ContactPage',
  head: {
    title: 'Seth Church | Contact Me',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Looking to get a project done? Need a new developer on your team? Shoot me a message.'
      }
    ],
  }
}
</script>

<style lang="scss" scoped>
  .contact {
    &__form {
      width: 100%;
    }
  }
</style>