<template>
    <div class="about">
      <SectionBody class="about__body" title="About Me">
        <!-- About Text -->

        <p>Hi, I'm Seth Church, a dedicated software engineer based in the United States. Currently working as a Full Stack developer.</p>
      
        <p>
          As a web developer with a strong passion for creating intuitive, fast, 
          and accessible applications, my approach development comes with a unique strategy. 
          By diving deep, beyond the surface of technologies, I ensure I am leveraging their full potential.
          With a foundation in both development and design, I'm dedicated to
          building experiences that are not only functional but also visually
          compelling.
        </p>

        <p>My Toolkit:</p>

        <!-- Skills Divider -->

        <ul class="about__skills">
          <SkillCard v-for="skill in skills" :icon="skill.icon" :name="skill.name" :key="skill.name"/>
        </ul> 

        <!-- Skills Divider End -->

        <!-- About Text -->
        <p>
          Are you looking to hire a developer? Looking to get something made? Need an opinion on a project? Don't hesitate to reach out to me on my 
          <nuxt-link class="about__link" to="/contact">contact page.</nuxt-link>
        </p>

      </SectionBody>

      <div class="about__planet">
        <svg preserveAspectRatio="xMinYMin meet" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="100%" height="100%" viewBox="0 0 793.007 995.699">
          <defs>
            <clipPath id="clip-path">
              <path id="Path_23" data-name="Path 23" d="M229.612,0c129.351,0,238.81,200.205,238.81,277.459s-104.86,139.88-234.211,139.88S0,354.712,0,277.459,100.261,0,229.612,0Z" transform="matrix(0.819, -0.574, 0.574, 0.819, 0, 268.676)" fill="#f29702"/>
            </clipPath>
          </defs>
          <g id="Group_18" data-name="Group 18" transform="translate(-107.972 33.63)">
            <g id="Group_15" data-name="Group 15" transform="matrix(0.914, -0.407, 0.407, 0.914, 203.48, 352.264)">
              <ellipse id="Ellipse_16" data-name="Ellipse 16" cx="230.938" cy="230.939" rx="230.938" ry="230.939" transform="translate(0 0)" fill="#f29702"/>
            </g>
            <g id="Group_16" data-name="Group 16" transform="translate(107.972 778.951) rotate(-59)">
              <path id="Path_22" data-name="Path 22" d="M473.992,0C735.771,0,947.984,79.591,947.984,177.771S735.771,355.543,473.992,355.543,0,275.952,0,177.771,212.213,0,473.992,0Z" transform="translate(0 0)" fill="#147de2"/>
              <path id="Path_26" data-name="Path 26" d="M328.209,231.325c181.265,0,328.209-51.784,328.209-115.663S509.473,0,328.209,0,0,51.784,0,115.662,146.944,231.325,328.209,231.325Z" transform="translate(145.783 62.109)" fill="#141618"/>
            </g>
            <g id="Mask_Group_2" data-name="Mask Group 2" transform="matrix(0.914, -0.407, 0.407, 0.914, 0, 253.432)" clip-path="url(#clip-path)">
              <path id="Path_27" data-name="Path 27" d="M230.938,0C358.482,0,461.877,103.395,461.877,230.939c0,95.53-58,177.513-140.8,212.684a230.1,230.1,0,0,1-90.142,18.254C103.395,461.877,0,358.483,0,230.939S103.395,0,230.938,0Z" transform="translate(145.689 173.051)" fill="#f29702"/>
            </g>
          </g>
        </svg>
      </div>
      
    </div>
</template>

<style lang="scss" scoped>

  @import '~/assets/css/variables';
  @import '~/assets/css/keyframes';

  .about {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    gap: 5rem;

    &__body {
      flex: 150%;
    }

    &__link {
      color: $blue;
      text-decoration: none;
    }

    &__skills {
      list-style-type: none;
      display: flex;
      width: 100%;
      min-width: 100%;
      gap: 1rem;
      padding: 0;
      flex-wrap: wrap;
      margin: 3rem 0;
    }
    
    &__planet {
        vertical-align: middle;
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
  }

    
  @media (max-width: 1300px) {
    .about {
      flex-direction: column-reverse;
      gap: 1rem;
      &__skills {
        justify-content: center;
        font-size: 0.9rem;
        gap: 0.9rem;
      }

      &__planet {
        width: 50%;
      }
    }
  }
</style>

<script>
export default {
  data: function() {
    return {
      skills: [
        { icon: 'devicon-javascript-plain', name: 'Javascript' },
        { icon: 'devicon-typescript-plain', name: 'Typescript'},
        { icon: 'devicon-docker-plain', name: 'Docker'},
        { icon: 'devicon-react-plain', name: 'React' },
        { icon: 'devicon-jest-plain', name: 'Jest' },
        { icon: 'devicon-mocha-plain', name: 'Mocha' },
        { icon: 'devicon-csharp-plain', name: 'C#' },
        { icon: 'devicon-nodejs-plain', name: 'Node.js' },
        { icon: 'devicon-express-original', name: 'Express.js' },
        { icon: 'devicon-mysql-plain', name: 'SQL' },
        { icon: 'devicon-html5-plain', name: 'HTML5' },
        { icon: 'devicon-css3-plain', name: 'CSS3' },
        { icon: 'devicon-sass-plain', name: 'Sass' },
        { icon: 'devicon-vuejs-plain', name: 'Vue.js' },
        { icon: 'devicon-python-plain', name: 'Python' },
        { icon: 'devicon-git-plain', name: 'Git' },
        { icon: 'devicon-graphql-plain', name: 'GraphQL' },
        { icon: 'devicon-mongodb-plain', name: 'MongoDB' },
        { icon: 'devicon-photoshop-plain', name: 'Photoshop' },
        { icon: 'devicon-illustrator-plain', name: 'Illustrator' },
        { icon: 'devicon-xd-plain', name: 'Adobe XD' },
      ]
    }
  },
  methods: {
    setupSkills() {
      const cards = document.querySelectorAll('.skill-card');
      cards.forEach(el => el.classList.add('skill-card--loading'));
    },
    addSkillsObserver() {
      const observer = new IntersectionObserver(entries => {
          for (const entry of entries) {
              if (entry.isIntersecting) {
                  this.clearSkills();
              }
          };
      });
      observer.observe(this.$el);
    },
    clearSkills() {
      const loadingCards = document.querySelectorAll('.skill-card--loading');
      loadingCards.forEach((el, i) => {
        setTimeout(() => {
          el.classList.remove('skill-card--loading');
        }, (100 * i) + 200);
      });
    }
  },
  mounted() {
   this.setupSkills(); 
   this.addSkillsObserver();
  }
}
</script>