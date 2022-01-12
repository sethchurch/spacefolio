<template>
  <div>
    <section class="landing">
      <header class="landing__header">
        <h1 class="landing__header-text">Hey, <br>I'm Seth<span class="text--orange">.</span></h1>
        <h2 class="landing__subheader text--blue">Software Engineer</h2>
        <a class="landing__link" href="/contact"><button class="landing__btn btn--orange btn--rounded">Contact Me!</button></a>
      </header>
    </section>
    <section class="portfolio">
      <div class="portfolio__header">
        <SectionBody title="My Portfolio">
          A small collection of projects I've worked on over the years. Interested in seeing more? Check out <a href='/work'>my work</a> page.
        </SectionBody>
        
        <a href="/work" class="portfolio__work-btn btn--orange btn--outline">See More!</a>
      </div>

      <PortfolioDisplay title="Community Leaderboard" desc="Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis." imgSrc="https://images.unsplash.com/photo-1641978909561-015aaa540119" />
      <PortfolioDisplay title="Course Tracker Mobile" desc="Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis." imgSrc="https://images.unsplash.com/photo-1641978909561-015aaa540119" />
      <PortfolioDisplay title="Project Name 3" desc="Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis." imgSrc="https://images.unsplash.com/photo-1641978909561-015aaa540119" />
    </section>
    <section class="about">
      <SectionBody title="About Me">
        Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis.
        Duis sit amet ante pellentesque, laoreet mauris sit amet, fermentum tellus. Duis purus massa, lobortis et urna id, pretium convallis enim. Praesent a sodales mi. Nullam fringilla est ornare tellus congue, eu imperdiet erat volutpat. Nam ut tempus eros. Aenean id nunc nec ante gravida fermentum. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Ut commodo quam sed sollicitudin feugiat.
        Quisque faucibus, tortor a blandit imperdiet, sapien orci vulputate felis, at sollicitudin diam urna in magna.
      </SectionBody>
    </section>
    <section class="contact">
      <SectionBody title="Contact Me">
         Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis.
      </SectionBody>
    </section>
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