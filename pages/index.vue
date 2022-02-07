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
    generateScene1() {
      let mouse = new THREE.Vector2();

      document.addEventListener('mousemove', onDocumentMouseMove, false);

      function onDocumentMouseMove(event) {
          event.preventDefault();
          mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
          mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
      }

      const canvas = document.querySelector('#landingCanvas');
      const renderer = new THREE.WebGLRenderer({canvas, antialias: true});

      renderer.setClearColor(0x0b0c0d); 

      const fov = 75;
      const aspect = 2; 
      const near = 0.1;
      const far = 100;
      const camera = new THREE.PerspectiveCamera(fov, aspect, near, far);

      camera.position.z = 5.5;
      camera.position.x = -2;

      const scene = new THREE.Scene();

      const geometry = new THREE.OctahedronGeometry(2.75, 2);
      const geometry2 = new THREE.OctahedronGeometry(1.5, 3);

      const material = new THREE.MeshBasicMaterial({color: 0xd88b0f, wireframe: true}); 
      const material2 = new THREE.MeshBasicMaterial({color: 0x111111}); 
      

      const sphere = new THREE.Mesh(geometry, material);
      const sphere2 = new THREE.Mesh(geometry2, material2);

      const color = 0xFFFFFF;
      const intensity = 1;
      const light = new THREE.DirectionalLight(color, intensity);
      light.position.set(-1, 2, 4);
      scene.add(light);

      scene.add(sphere);
      scene.add(sphere2);

      renderer.setPixelRatio(window.devicePixelRatio * 5);
      renderer.render(scene, camera);
    
      function render(time) {
        time *= 0.001;
      
        sphere.rotation.x = time / 3;
        sphere.rotation.y = time / 3;

        sphere2.rotation.x = -time / 2;
        sphere2.rotation.y = -time / 2;


        sphere.position.lerp(new THREE.Vector3(mouse.x, mouse.y + Math.sin(time * 2) * 0.75, sphere2.z), 0.01);
        sphere2.position.lerp(new THREE.Vector3(mouse.x, mouse.y + Math.sin(time * 2) * 0.5, sphere2.z), 0.2)

        camera.aspect = canvas.clientWidth / canvas.clientHeight;
        camera.updateProjectionMatrix();
      
        renderer.render(scene, camera);
      
        requestAnimationFrame(render);
      }
      requestAnimationFrame(render);
    },
    generateScene2() {
      let mouse = new THREE.Vector2();

      document.addEventListener('mousemove', onDocumentMouseMove, false);

      function onDocumentMouseMove(event) {
          event.preventDefault();
          mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
          mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
      }

      const canvas = document.querySelector('#landingCanvas');
      const renderer = new THREE.WebGLRenderer({canvas, antialias: true});

      renderer.setClearColor(0x0b0c0d); 
      const camera = new THREE.PerspectiveCamera( 75, 2, 0.1, 50);

      camera.position.z = 5;
      camera.position.x = -2;

      const scene = new THREE.Scene();


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

      // Int -> THREE.Mesh[]
      // produces a number of rings based on the given int

      const getRingList = n => {
        let ringArray = [];

        for (let i = 2; i < n + 2; i++) {
          const path = new CustomCircleCurve( i + (0.5 * i));
          const geometry = new THREE.TubeGeometry( path, 64, 0.01, 8, false );
          const material = new THREE.MeshBasicMaterial({color: 0x1F3B58}); 
          const ring = new THREE.Mesh( geometry, material);

          ring.rotation.x = 2.55;
          ring.rotation.y = 0.35;

          ringArray.push(ring);
        }

        return ringArray;
      }

      const rings = getRingList(10);

      const geometry = new THREE.SphereGeometry(1.5, 30, 30);
      const material = new THREE.MeshBasicMaterial({color: 0xd88b0f}); 
      const sphere = new THREE.Mesh( geometry, material);

      sphere.rotation.x = 90;

      const light = new THREE.DirectionalLight( 0xFFFFFF, 1);
      light.position.set(-1, 2, 4);
      scene.add(light);

      scene.add(sphere);
      rings.forEach(ring => {
        scene.add(ring);
      });

      renderer.setPixelRatio(window.devicePixelRatio * 4);
      renderer.render(scene, camera);
    
      function render(time) {
        time *= 0.001;

        sphere.position.lerp(new THREE.Vector3(mouse.x, mouse.y, sphere.z), 0.02);
        rings.forEach((ring, i) => {
          ring.position.lerp(new THREE.Vector3(mouse.x, mouse.y, sphere.z), (0.005 * rings.length) / ((i + 1) * 2) );
        });

        camera.aspect = canvas.clientWidth / canvas.clientHeight;
        camera.updateProjectionMatrix();

        renderer.render(scene, camera);
        requestAnimationFrame(render);
      }
      requestAnimationFrame(render);
    }
  },
  mounted: function() {
    // this.generateScene1();
    this.generateScene2();
  }
}
</script>

<style lang="scss" scoped>
  @import '~/assets/css/landing';
</style>