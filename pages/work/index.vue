<template>
  <main class="work">
    <SectionBody class="work__header" title="My Work">
      <p>
        Here's a list of projects I've worked on over the years. I'm proficent
        in many different stacks and technologies.
      </p>
    </SectionBody>

    <div class="work__wrapper">
      <div class="work__trail">
        <div class="work__ship">
          <img src="/ship.svg" alt="A space ship!" />
        </div>
      </div>

      <section class="work__portfolio-container">
        <PortfolioDisplay
          :skills="['Next.js', 'React', 'TailwindCSS', 'OpenAI']"
          title="Project Spellbook"
          desc="Project Spellbook is a full-stack web application designed to enhance the Dungeons & Dragons experience by simplifying character creation. Utilizing OpenAI's language model, it offers intelligent feature suggestions, allowing players to generate and store characters with efficiency."
          imgSrc="/projectSpellbook.png"
          gitLink="https://project-spellbook.vercel.app/"
        />

        <PortfolioDisplay
          :skills="['Xamarin', 'C#', 'SQLite']"
          title="Course Tracker Mobile"
          desc="A native android application developed in C# using the Xamarin Forms framework and designed to aid students to track their courses for a term and keep an eye on any upcoming due dates. It utilizes an SQLite database to store and organize user-relevant data and an interface that was written in XAML."
          imgSrc="/courseTracker.png"
          gitLink="https://github.com/sethchurch/Course-Tracker-Mobile"
        />

        <PortfolioDisplay
          :skills="['Discord.JS', 'Javascript', 'MongoDB']"
          title="Torchbearer Armory Bot"
          desc="A Discord.JS application designed to maintain and organize inventory for a Dungeon and Dragons community server. Programmed entirely in vanilla javascript and hosted on Netlify with a MongoDB database hosted on mLab."
          imgSrc="/armory.png"
          gitLink="https://github.com/sethchurch/discord-armory-5e"
        />

        <PortfolioDisplay
          :skills="['Vue.JS', 'SASS', 'GraphQL']"
          title="Community Leaderboard"
          desc="A Leaderboard web app which was developed to track and display scores from a community game server. Designed in Illustrator and implemented in Vue.JS, it interfaces a GraphQL API to pull and display the latest information about the players."
          imgSrc="https://i.imgur.com/vbsylK9.png"
          gitLink="https://github.com/sethchurch/bb-leaderboards"
        />

        <PortfolioDisplay
          :skills="['MySQL', 'C#', 'Visual Studio']"
          title="Client Scheduler"
          desc="A C# scheduler application designed to manage multiple customers and their associated appointments."
          imgSrc="/schedule.png"
          gitLink="https://github.com/sethchurch/Client-Scheduler"
        />

        <PortfolioDisplay
          :skills="['Node.JS', 'Pug', 'MongoDB']"
          title="Shouter"
          desc="Social media platform inspired by twitter built on NodeJS with the Express framework."
          imgSrc="https://i.imgur.com/Ei1617F.png"
          gitLink="https://github.com/sethchurch/Shouter"
        />
      </section>
    </div>
  </main>
</template>

<script>
export default {
  name: "WorkPage",
  head: {
    title: "Seth Church | My Work",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "Take a look around my work page. I've worked on all kinds of projects over the years..",
      },
    ],
  },
  methods: {
    bindShipToScrollOffset() {
      const ship = document.querySelector(".work__ship");

      const extractPercentFromCSS = (stringProp) => {
        try {
          return parseInt(stringProp.replace("%", ""));
        } catch (e) {
          return 0;
        }
      };

      window.addEventListener("scroll", () => {
        const offset =
          window.scrollY / (document.body.offsetHeight - window.innerHeight);
        // rotate ship according to scroll direction and apply offset
        const movingDownFlag =
          extractPercentFromCSS(ship.style.top) > offset * 90;
        ship.style.transform = `rotate(${movingDownFlag ? 180 : 0}deg)`;
        ship.style.top = `${offset * 90}%`;
      });
    },
  },
  mounted: function () {
    this.bindShipToScrollOffset();
  },
};
</script>

<style lang="scss" scoped>
@import "~/assets/css/work";
</style>
