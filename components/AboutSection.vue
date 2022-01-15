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
      </SectionBody>

      <div class="about__planet"></div>
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