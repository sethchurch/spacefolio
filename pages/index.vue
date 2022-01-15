<template>
  <div class="container">
    <!-- Header -->
    <section class="section landing">
      <header class="landing__header">
        <h1 class="landing__header-text">Hey, <br>I'm Seth<span class="text--orange">.</span></h1>
        <h2 class="landing__subheader text--blue">Software Engineer</h2>
        <a class="landing__link" href="/contact"><button class="landing__btn btn--orange btn--rounded">Contact Me!</button></a>
      </header>
    </section>
    <!-- Header End -->

    <!-- Portfolio Section -->
    <section class="section landing-portfolio">
      <div class="landing-portfolio__header">
        <SectionBody class="section__header" title="My Portfolio">
          A small collection of projects I've worked on over the years. Interested in seeing more? Check out <a class="section__work-link" href='/work'>my work</a> page.
        </SectionBody>
        
        <a href="/work" class="landing-portfolio__work-btn btn--orange btn--outline">See More!</a>
      </div>

      <PortfolioDisplay title="Community Leaderboard" desc="Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis." imgSrc="https://images.unsplash.com/photo-1641978909561-015aaa540119" />
      <PortfolioDisplay title="Course Tracker Mobile" desc="Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis." imgSrc="https://images.unsplash.com/photo-1641978909561-015aaa540119" />
      <PortfolioDisplay title="Project Name 3" desc="Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis." imgSrc="https://images.unsplash.com/photo-1641978909561-015aaa540119" />
    </section>
    <!-- Portfolio Section End -->

    <!-- About Section -->
    <section class="section landing-about">
      <AboutSection />
    </section>
    <!-- About Section End -->

    <!-- Contact Section -->
    <section class="section landing-contact">
      <SectionBody class="section__header" title="Contact Me">
         Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis.
      </SectionBody>

      <ContactForm class="landing-contact__form" />
    </section>
    <!-- Contact Section  End -->

    <!-- Footer -->
    <footer class="footer">
      
    </footer>
    <!-- Footer End -->
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style lang="scss" scoped>
  @import '~/assets/css/landing';
</style>