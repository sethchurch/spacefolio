<template>
  <div class="landing-container">
    <!-- Header -->
    <section class="section landing">
      <div class="container">
        <header class="landing__header">
          <h1 class="landing__header-text">
            Hey, 
            <br>
            <span class="landing__name">I'm Seth<span class="text--orange">.</span></span>
            <br> 
            <div class="landing__subheader text--blue">{{ this.jobTitle }}</div>
          </h1>
          <a class="landing__link" href="/contact"><button class="landing__btn btn--orange btn--outline">Contact Me!</button></a>
        </header>
      </div>
      <canvas class="landing__canvas" id="landingCanvas" />
    </section>
    <!-- Header End -->

    <!-- Portfolio Section -->
    <section class="section landing-portfolio">
      <div class="container">
        <div class="landing-portfolio__header">
          <SectionBody class="section__header" title="My Portfolio">
            <p>Here's a few highlights from projects I've worked on over the years. Interested in seeing more? Check out <a class="section__work-link" href='/work'>my work</a> page.</p>
          </SectionBody>
          
          <a href="/work" class="landing-portfolio__work-btn btn--orange btn--outline">See more</a>
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
import * as THREE from 'three';

export default {
  name: 'IndexPage',
  methods: {
    // THREE.JS Landing Page Scenes 
    generateOrbitalScene() {
      let mouse = new THREE.Vector2();
      document.addEventListener('mousemove', (event) => {
        event.preventDefault();
        mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
        mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
      }, false);

      class CustomCircleCurve extends THREE.Curve {
        constructor( scale = 1 ) {
          super();
          this.scale = scale;
        }

        getPoint( t, optionalTarget = new THREE.Vector3() ) {
          const tx = Math.cos( 2 * Math.PI * t );
          const ty = Math.sin( 2 * Math.PI * t );
          const tz = 0;
          return optionalTarget.set( tx, ty, tz ).multiplyScalar( this.scale );
        }
      }

      // Int -> THREE.Mesh[] Int[]
      // produces a number of rings based on the given int

      const getRingList = n => {
        let ringArray = [];
        let ringRadArray = [];

        for (let i = 2; i < n + 2; i++) {
          const radius = i + (i * (i / 5));

          const path = new CustomCircleCurve(radius);
          const geometry = new THREE.TubeGeometry( path, 96, 0.015, 8, false );
          const material = new THREE.MeshBasicMaterial({color: 0x1F3B58}); 
        
          material.transparent = true;
          material.opacity = 1 / i;

          const ring = new THREE.Mesh( geometry, material);

          ringRadArray.push(radius);
          ringArray.push(ring);
        }

        return [ringArray, ringRadArray];
      }

      const createSphere = (radius, color) => {
        const geometry = new THREE.SphereGeometry(radius, 30, 30);
        const material = new THREE.MeshBasicMaterial({color: color}); 
        const sphere = new THREE.Mesh( geometry, material);
        return sphere;
      }

      const canvas = document.querySelector('#landingCanvas');
      const renderer = new THREE.WebGLRenderer({canvas, antialias: true});
      const scene = new THREE.Scene();
      const camera = new THREE.PerspectiveCamera( 75, 2, 0.1, 100);

      renderer.setClearColor(0x0b0c0d); 
      camera.position.set(2, -3, 5)

      const [rings, ringsRadius] = getRingList(15);
      
      const sunMesh = createSphere(1.4, 0xd88b0f);
      const planetMesh = createSphere(0.2, 0x163E66);

      scene.add(sunMesh);
      scene.add(planetMesh);

      for (let ring of rings) {
        scene.add(ring);
      }
      
      renderer.setPixelRatio(window.devicePixelRatio * 4);
      renderer.render(scene, camera);
      
      // start planet in correct position
      planetMesh.position.set(Math.cos(0) * ringsRadius[0], Math.sin(0) * ringsRadius[0], 0);
      
      const CAM_OFFSET_X = 1;
      const CAM_OFFSET_Y = -4;
      const SUN_LERP_SPEED = 0.05;
      const CAMERA_LERP_SPEED = 0.02;

      function render(time) {
        time *= 0.001;

        const BOUNCE = Math.sin(time / 5) / 3;
        const bounceWithMouseOffset = BOUNCE + mouse.y;

        sunMesh.position.lerp(new THREE.Vector3(sunMesh.x, sunMesh.y, bounceWithMouseOffset), SUN_LERP_SPEED);
        camera.position.lerp(new THREE.Vector3(-mouse.x + CAM_OFFSET_X, -bounceWithMouseOffset + CAM_OFFSET_Y, camera.position.z), CAMERA_LERP_SPEED);

        for (let [ringIndex, ring] of rings.entries()) {
          const ORBIT_LERP_SPEED = (0.005 * rings.length) / ((ringIndex + 1) * 2);
          ring.position.lerp(new THREE.Vector3(ring.x, ring.y, bounceWithMouseOffset), ORBIT_LERP_SPEED);

          if(ringIndex != 0) continue;
          const effectiveRadius = ringsRadius[ringIndex];
          planetMesh.position.lerp(new THREE.Vector3(Math.cos(time) * effectiveRadius, Math.sin(time) * effectiveRadius, bounceWithMouseOffset), ORBIT_LERP_SPEED);
        }

        camera.lookAt(new THREE.Vector3(sunMesh.position.x - 2, sunMesh.position.y + 1, sunMesh.position.z));
        camera.aspect = canvas.clientWidth / canvas.clientHeight;
        camera.updateProjectionMatrix();
        renderer.render(scene, camera);
        requestAnimationFrame(render);
      }
      
      requestAnimationFrame(render);
    },
    animateJobTitle() {
      const index = Math.floor(Math.random() * this.titleList.length - 1);

      // get title from list but dont include already selected title
      let selectedTitle = this.titleList.filter(el => el !== this.jobTitle)[index].split('');

      // set title to first character to keep up content spacing
      this.jobTitle = selectedTitle.shift();

      // animate title
      for(let i = 1; i < selectedTitle.length + 1; i++) {
        let interval = 50 * i;
        setTimeout(() => {
          this.jobTitle += selectedTitle.shift();
        }, interval);
      }

    }
  },
  mounted: function() {
    this.generateOrbitalScene();
    setInterval(() => this.animateJobTitle(), 5000)
  },
  data() {
    return {
      jobTitle: 'Web Developer',
      titleList: ['Software Engineer', 'Front-End Developer', 'Web Developer', 'Creative Developer', 'Software Developer', 'D&D Enthusiast', 'Character Illustrator', 'Full Stack Developer']
    }
  },
  head() {
    return {
      title: `Seth Church | ${ this.jobTitle }`,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Hey There! I\'m a Creative Software Developer with a passion for designing and building applications. Looking to collab? Check out my portfolio and get in touch.'
        }
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
  @import '~/assets/css/landing';
</style>