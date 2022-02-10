<template>
  <main class="work">
      <SectionBody class="work__header" title="My Work" />

      <section class="work__portfolio-container">
        <PortfolioDisplay 
          :skills="['Xamarin', 'C#', 'SQLite']" 
          title="Course Tracker Mobile" 
          desc="A native android application developed in C# using the Xamarin Forms framework and designed to aid students to track their courses for a term and keep an eye on any upcoming due dates. It utilizes an SQLite database to store and organize user-relevant data and an interface that was written in XAML." 
          imgSrc="https://camo.githubusercontent.com/02da002b5866c049b8a4e62fcc7bfff13c4635b14dc90d42cfca67ebb35f0964/68747470733a2f2f692e696d6775722e636f6d2f32677659574f332e706e67"  
          gitLink="https://github.com/iEnder/Course-Tracker-Mobile" 
        />

        <PortfolioDisplay 
          :skills="['Discord.JS', 'Javascript', 'MongoDB']" 
          title="Torchbearer Armory Bot" 
          desc="A Discord.JS application designed to maintain and organize inventory for a Dungeon and Dragons community server. Programmed entirely in vanilla javascript and hosted on Netlify with a MongoDB database hosted on mLab." 
          imgSrc="https://camo.githubusercontent.com/074efab13f1e347846539e047ac1cd10644b19bc611ed15149e7aec0df876312/68747470733a2f2f692e696d6775722e636f6d2f4b4b6f657268622e706e67"  
          gitLink="https://github.com/iEnder/Discord5eArmory" 
        />

        <PortfolioDisplay 
          :skills="['Vue.JS', 'SASS', 'GraphQL']"
          title="Community Leaderboard" 
          desc="A Leaderboard web app which was developed to track and display scores from a community game server. Designed in Illustrator and implemented in Vue.JS, it interfaces a GraphQL API to pull and display the latest information about the players." 
          imgSrc="https://i.imgur.com/vbsylK9.png" 
          gitLink="https://github.com/iEnder/bb-leaderboards"
        />

        <PortfolioDisplay 
          :skills="['MySQL', 'C#', 'Visual Studio']" 
          title="Client Scheduler" 
          desc="A native android application developed in C# using the Xamarin Forms framework and designed to aid students to track their courses for a term and keep an eye on any upcoming due dates. It utilizes an SQLite database to store and organize user-relevant data and an interface that was written in XAML." 
          imgSrc="https://camo.githubusercontent.com/c3754adcd690eabe6efbc8864a80f8b1a0eaf99b8d242409e1b857e23ee1a1f6/68747470733a2f2f692e696d6775722e636f6d2f4d764f506230372e706e67"  
          gitLink="https://github.com/iEnder/Course-Tracker-Mobile" 
        />

        <PortfolioDisplay 
          :skills="['MySQL', 'C#', 'Visual Studio']" 
          title="Client Scheduler" 
          desc="A native android application developed in C# using the Xamarin Forms framework and designed to aid students to track their courses for a term and keep an eye on any upcoming due dates. It utilizes an SQLite database to store and organize user-relevant data and an interface that was written in XAML." 
          imgSrc="https://camo.githubusercontent.com/eb20edfe296460d3c5750a587398964cd59e5036983f7e2812d957fbad4487f7/68747470733a2f2f692e696d6775722e636f6d2f745769487746482e706e67"  
          gitLink="https://github.com/iEnder/Course-Tracker-Mobile" 
        />
        </section>
    
  </main>
</template>

<script>
export default {
  name: 'WorkPage',
  head: {
    title: 'Seth Church | My Work',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Take a look around my work page. I\'ve worked on all kinds of projects over the years..'
      }
    ],
  }
}
</script>

<style lang="scss" scoped>
  @import '~/assets/css/work';
</style>