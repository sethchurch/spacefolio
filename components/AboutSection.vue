<template>
    <div class="about">
        <SectionBody class="about__body" title="About Me">
        Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis.
        <br>
        <br>
        Duis sit amet ante pellentesque, laoreet mauris sit amet, fermentum tellus. Duis purus massa, lobortis et urna id, pretium convallis enim. Praesent a sodales mi. Nullam fringilla est ornare tellus congue, eu imperdiet erat volutpat. Nam ut tempus eros. Aenean id nunc nec ante gravida fermentum. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Ut commodo quam sed sollicitudin feugiat.
        <br>
        <br>
        Quisque faucibus, tortor a blandit imperdiet, sapien orci vulputate felis, at sollicitudin diam urna in magna.
        <ul class="about__skills">
          <li class="about__skills-item" v-for="skill in skills">
            <i class="about__skills-icon" :class="skill.icon" />
            <p class="about__skills-name" >{{ skill.name }}</p>
          </li>
        </ul>
        <!-- <ul class="about__skills">
          <li class="about__skills-item" v-for="skill in skills">
            <fa class="about__skills-icon" :icon="skill.icon" />
            <p class="about__skills-name" >{{ skill.name }}</p>
          </li>
        </ul> -->
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

    &__skills {
      list-style-type: none;
      display: flex;
      width: 100%;
      gap: 1rem;
      padding: 0;
      flex-wrap: wrap;
    }

    &__skills-item {
      display: flex;
      flex-direction: column;
      height: 7rem;
      width: 7rem;
      background: lighten($baseBG, 10%);
      justify-content: center;
      align-items: center;
      text-align: center;
      position: relative;
    }

    &__skills-icon {
      font-size: 3.5rem;
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