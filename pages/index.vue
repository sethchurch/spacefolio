<template>
  <div class="landing-container">

    <div class="warning">This website is under active construction. Bear with me while the details are ironed out.</div>

    <!-- Header -->
    <section class="section landing">
      <div class="container">
        <header class="landing__header">
          <h1 class="landing__header-text">Hey, <br>I'm Seth<span class="text--orange">.</span></h1>
          <h2 class="landing__subheader text--blue">Software Engineer</h2>
          <a class="landing__link" href="/contact"><button class="landing__btn btn--orange btn--rounded">Contact Me!</button></a>
        </header>
      </div>
    </section>
    <!-- Header End -->

    <!-- Portfolio Section -->
    <section class="section landing-portfolio">
      <div class="container">
        <div class="landing-portfolio__header">
          <SectionBody class="section__header" title="My Portfolio">
            <p>Here's a few highlights from projects I've worked on over the years. Interested in seeing more? Check out <a class="section__work-link" href='/work'>my work</a> page.</p>
          </SectionBody>
          
          <a href="/work" class="landing-portfolio__work-btn btn--orange btn--outline">See More!</a>
        </div>

        <PortfolioPlanet 
          :planet="true" 
          :skills="['Xamarin', 'C#', 'SQLite']" 
          title="Course Tracker Mobile" 
          desc="A native android application developed in C# using the Xamarin Forms framework and designed to aid students to track their courses for a term and keep an eye on any upcoming due dates. It utilizes an SQLite database to store and organize user-relevant data and an interface that was written in XAML." 
          imgSrc="https://camo.githubusercontent.com/02da002b5866c049b8a4e62fcc7bfff13c4635b14dc90d42cfca67ebb35f0964/68747470733a2f2f692e696d6775722e636f6d2f32677659574f332e706e67"  
          gitLink="https://github.com/iEnder/Course-Tracker-Mobile" 
        />

        <PortfolioPlanet 
          :planet="true" 
          :skills="['Discord.JS', 'Javascript', 'MongoDB']" 
          title="Torchbearer Armory Bot" 
          desc="A Discord.JS application designed to maintain and organize inventory for a Dungeon and Dragons community server. Programmed entirely in vanilla javascript and hosted on Netlify with a MongoDB database hosted on mLab." 
          imgSrc="https://camo.githubusercontent.com/074efab13f1e347846539e047ac1cd10644b19bc611ed15149e7aec0df876312/68747470733a2f2f692e696d6775722e636f6d2f4b4b6f657268622e706e67"  
          gitLink="https://github.com/iEnder/Discord5eArmory" 
          :flip="true" 
        />

        <PortfolioPlanet 
          :planet="true"
          :skills="['Vue.JS', 'SASS', 'GraphQL']"
          title="Community Leaderboard" 
          desc="A Leaderboard web app which was developed to track and display scores from a community game server. Designed in Illustrator and implemented in Vue.JS, it interfaces a GraphQL API to pull and display the latest information about the players." 
          imgSrc="https://i.imgur.com/vbsylK9.png" 
          gitLink="https://github.com/iEnder/bb-leaderboards"
        />
      </div>
    </section>
    <!-- Portfolio Section End -->

    <!-- About Section -->
    <section class="section landing-about">
      <div class="container">
        <AboutSection class="section__header" />  
      </div>
    </section>
    <!-- About Section End -->

    <!-- Contact Section -->
    <section class="section landing-contact">
      <div class="container">
        <SectionBody class="section__header" title="Contact Me">
          <p>If you're looking to collaborate on a project, get in touch about a position, or say hi, feel free to use the form below. I'll be in touch with you as soon as I can.</p>
        </SectionBody>

        <ContactForm class="landing-contact__form" />
      </div>
    </section>
    <!-- Contact Section  End -->

    <!-- Footer -->
    <footer class="footer">
      <p>Designed and Developed By Seth Church</p>
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