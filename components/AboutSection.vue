<template>
    <div class="about">
        <SectionBody class="section__header" title="About Me">
        Integer eget magna nisi. Vivamus sit amet leo erat. Praesent enim risus, mattis sit amet mollis nec, facilisis et eros. Phasellus lobortis varius ligula. Vivamus pretium ut odio eget facilisis.
        <br>
        <br>
        Duis sit amet ante pellentesque, laoreet mauris sit amet, fermentum tellus. Duis purus massa, lobortis et urna id, pretium convallis enim. Praesent a sodales mi. Nullam fringilla est ornare tellus congue, eu imperdiet erat volutpat. Nam ut tempus eros. Aenean id nunc nec ante gravida fermentum. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Ut commodo quam sed sollicitudin feugiat.
        <br>
        <br>
        Quisque faucibus, tortor a blandit imperdiet, sapien orci vulputate felis, at sollicitudin diam urna in magna.
        <ul class="about__skills">
          <li class="about__skills-item" v-for="skill in skills">
            <fa class="about__skills-icon" :icon="skill.icon" />
            <p class="about__skills-name" >{{ skill.name }}</p>
          </li>
        </ul>
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
    }

    &__skills-item {
      display: flex;
      flex-direction: column;
      height: 8rem;
      width: 8rem;
      background: lighten($baseBG, 10%);
      justify-content: center;
      align-items: center;
      text-align: center;
      position: relative;
    }

    &__skills-icon {
      font-size: 4rem;
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
        { icon: ['fab', 'js'], name: 'Javascript' },
        { icon: ['fab', 'react'], name: 'React' },
        { icon: ['fab', 'vuejs'], name: 'Vue.js' },
        { icon: ['fab', 'html5'], name: 'HTML5' },
        { icon: ['fab', 'css3-alt'], name: 'CSS3' },
        { icon: ['fab', 'sass'], name: 'Sass' },
        { icon: ['fab', 'git-alt'], name: 'Git' },
        { icon: ['fab', 'node-js'], name: 'Node.js' },
      ]
    }
  }
}
</script>