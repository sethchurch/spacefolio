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

      <div class="about__planet">
        <!-- <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="793.007" height="995.699" viewBox="0 0 793.007 995.699">
          <defs>
            <clipPath id="clip-path">
              <path id="Path_232" data-name="Path 232" d="M229.612,0c129.351,0,238.81,200.205,238.81,277.459s-104.86,139.88-234.211,139.88S0,354.712,0,277.459,100.261,0,229.612,0Z" transform="matrix(0.819, -0.574, 0.574, 0.819, 0, 268.676)" fill="#f29702"/>
            </clipPath>
          </defs>
          <g id="Group_18" data-name="Group 18" transform="translate(-107.972 33.63)">
            <g id="Group_15" data-name="Group 15" transform="matrix(0.914, -0.407, 0.407, 0.914, 203.48, 352.264)">
              <ellipse id="Ellipse_16" data-name="Ellipse 16" cx="230.938" cy="230.939" rx="230.938" ry="230.939" transform="translate(0 0)" fill="#f29702"/>
            </g>
            <g id="Group_16" data-name="Group 16" transform="translate(107.972 778.951) rotate(-59)">
              <path id="Path_22" data-name="Path 22" d="M473.992,0C735.771,0,947.984,79.591,947.984,177.771S735.771,355.543,473.992,355.543,0,275.952,0,177.771,212.213,0,473.992,0Z" transform="translate(0 0)" fill="#147de2"/>
              <path id="Path_26" data-name="Path 26" d="M328.209,231.325c181.265,0,328.209-51.784,328.209-115.663S509.473,0,328.209,0,0,51.784,0,115.662,146.944,231.325,328.209,231.325Z" transform="translate(145.783 62.109)" fill="#141618"/>
            <g id="Mask_Group_2" data-name="Mask Group 2" transform="matrix(0.914, -0.407, 0.407, 0.914, 0, 253.432)" clip-path="url(#clip-path)">
              <path id="Path_27" data-name="Path 27" d="M230.938,0C358.482,0,461.877,103.395,461.877,230.939c0,95.53-58,177.513-140.8,212.684a230.1,230.1,0,0,1-90.142,18.254C103.395,461.877,0,358.483,0,230.939S103.395,0,230.938,0Z" transform="translate(145.689 173.051)" fill="#f29702"/>
            </g>
            </g>
          </g>
        </svg> -->
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