<template>
    <div class="about">
        <SectionBody class="about__body" title="About Me">
        <p>Names Gregory Seth Church though most people just call me Seth. I'm an avid learner with a passion for many talents and interests, one road of which led to me becoming an excellent designer and builder of digital products.</p>
        <p>
          I strive to make the web faster, more accessible, visually appealing, and easy to use as a developer. I'm constantly looking for opportunities to improve and better myself as a developer and learn new technologies. I'm never quite satisfied with learning simply the high-level concepts of technology; if you're interested in what skills I've picked up over the years, here's what I work with currently: 
           <!-- in what I'm working with at the moment check the planet. -->
        </p>
        <ul class="about__skills">
          <li class="about__skills-item" v-for="skill in skills">
            <i class="about__skills-icon" :class="skill.icon" />
            <p class="about__skills-name" >{{ skill.name }}</p>
          </li>
        </ul>
        <p>Are you looking to hire a developer? Looking to get something made? Need an opinion on a project? Don't hesitate to reach out to me on my <nuxt-link class="about__link" to="/contact">contact page.</nuxt-link></p>
      </SectionBody>

      <div class="about__planet">

      </div>
    </div>
</template>

<style lang="scss" scoped>

  @import '~/assets/css/variables';

  .about {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    gap: 5rem;

    &__link {
      color: $blue;
      text-decoration: none;
    }

    &__skills {
      list-style-type: none;
      display: flex;
      width: 100%;
      gap: 1rem;
      padding: 0;
      flex-wrap: wrap;
      justify-content: center;
    }

    &__skills-item {
      display: flex;
      flex-direction: column;
      height: 7rem;
      width: 7rem;
      border-radius: 100%;
      background: lighten($baseBG, 10%);
      justify-content: center;
      align-items: center;
      text-align: center;
      position: relative;
    }

    &__skills-icon {
      font-size: 3rem;
    }

    &__skills-name {
      // position: absolute;
      // bottom: 0.5rem;
      margin: 0;
      margin-top: 0.5rem;
    }
    
    &__planet {
        width: 25rem;
        height: 25rem;
        border-radius: 100%;
        background: $orange;
        margin: 0 auto;
        flex-shrink: 0;
    }
  }
</style>

<script>
export default {
  data: function() {
    return {
      skills: [
        { icon: 'devicon-javascript-plain', name: 'Javascript' },
        { icon: 'devicon-python-plain', name: 'Python' },
        { icon: 'devicon-csharp-plain', name: 'C#' },
        { icon: 'devicon-graphql-plain', name: 'GraphQL' },
        { icon: 'devicon-react-plain', name: 'React' },
        { icon: 'devicon-vuejs-plain', name: 'Vue.js' },
        { icon: 'devicon-html5-plain', name: 'HTML5' },
        { icon: 'devicon-css3-plain', name: 'CSS3' },
        { icon: 'devicon-sass-plain', name: 'Sass' },
        { icon: 'devicon-git-plain', name: 'Git' },
        { icon: 'devicon-mysql-plain', name: 'MySQL' },
        { icon: 'devicon-mongodb-plain', name: 'MongoDB' },
        { icon: 'devicon-nodejs-plain', name: 'Node.js' },
        { icon: 'devicon-photoshop-plain', name: 'Photoshop' },
        { icon: 'devicon-illustrator-plain', name: 'Illustrator' },
        { icon: 'devicon-xd-plain', name: 'Adobe XD' },
      ]
    }
  }
}
</script>