<script lang="ts">
    let showVideo=false
  const services = [
    { img: "/lettuce.svg", title: "UX DESIGN" },
    { img: "/tomato.svg", title: "UI DESIGN" },
    { img: "/cheese.svg", title: "WEBSITE DEVELOPMENT" },
    { img: "/cucumber.svg", title: "mobile app development" },
    { title: "ECOMMERCE", img: "/orange.svg" },
    { title: "CUSTOMER LOYALTY", img: "/kiwi.svg" },
    { title: "digital transformation", img: "/watermelon.svg" },
    { title: "digital marketing", img: "/corn.svg" },
    { img: "/apple.svg", title: "BRANDING" },
  ];
</script>

<div class="flex flex-col items-center lg:px-[200px]">
  <div
    class=" flex items-end font-bold text-[28px] mt-[125px] leading-9 decoration-wavy text-[#262626] underline decoration-[#26C6D0] underline-offset-8 p-2 tracking-[1px]"
  >
    <div>ABOUT DIGISALAD</div>
    <div class="header" />
  </div>
  <div class="mt-[90px] relative" class:p-6={showVideo}>
{#if showVideo}
<button class="w-[22px] h-[22px] absolute right-0 top-0" on:click={()=>showVideo=false}>
    <img src="/close.svg" alt="" />
  </button>
<iframe width="720" height="315" src="https://www.youtube.com/embed/IeIRJ9jZ5Ro?autoplay=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

{:else}
      <img
      src="/video-thumbnail.png"
      alt="video-thumbnail"
      class="block"
      />
      <button class="absolute top-1/2 right-1/2 translate-x-1/2 translate-y-[-50%]" on:click={()=>showVideo=true}>
          <img src="/play.svg" alt="">
        </button>
        {/if}
    </div>
  <p
    class="font-normal text-[16px] tracking-[1px] leading-[28px] text-center mx-auto px-10 my-[30px]"
  >
    Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper
    bibendum bibendum. Duis tincidunt urna non pretium porta. Nam condimentum
    vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu tellus tortor.
    Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc.
    Donec elit ante, eleifend a dolor et, venenatis facilisis dolor. In feugiat
    orci odio, sed lacinia sem elementum quis. Aliquam consectetur, eros et
    vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus.
    Cras lobortis molestie faucibus.
  </p>
  <button class="btn">VIEW MORE</button>
</div>
<div class=" relative">
  <div class="absolute rounded-ss-3xl bottom-0 bg-[#26C6D0] w-full h-[50%]" />
  <div
    class=" ml-[100px] py-[65px] bg-white relative pl-[70px] rounded-s-3xl rounded-ee-2xl flex"
  >
    <div>
      <div
        class=" flex items-end font-bold text-[28px] mb-[30px] leading-9 decoration-wavy text-[#262626] underline decoration-[#26C6D0] underline-offset-8 p-2 tracking-[1px]"
      >
        <div>AWARDS</div>
        <div class="header" />
      </div>
      <div class="max-w-[450px]">
        Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras
        ullamcorper bibendum bibendum. Duis tincidunt urna non pretium porta.
        Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis.
        Nunc eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci.
        Donec id dignissim nunc.
      </div>
    </div>
    <div class="grid grid-cols-2 text-center ml-[35px]">
      <img src="image_1.png" alt="award" class="w-full" />
      <img src="image_1.png" alt="award" class="w-full" />
      <img src="image_1.png" alt="award" class="w-full" />
      <img src="image_1.png" alt="award" class="w-full" />
    </div>
  </div>
</div>
<div
  class="bg-[#26C6D0] flex flex-col items-center pt-[100px] text-white px-[200px]"
>
  <div
    class=" flex items-end font-bold text-[28px] mb-[30px] leading-9 decoration-wavy text-white underline decoration-[#585880] underline-offset-8 p-2 tracking-[1px]"
  >
    <div>OUR INGRADIENTS</div>
    <div class="header" />
  </div>
  <p class="mb-[30px]">
    Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper
    bibendum bibendum. Duis tincidunt urna non pretium porta. Nam condimentum
    vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu tellus tortor.
    Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc.
    Donec elit ante, eleifend a dolor et, venenatis facilisis dolor. In feugiat
    orci odio, sed lacinia sem elementum quis. Aliquam consectetur, eros et
    vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus.
    Cras lobortis molestie faucibus.
  </p>
  <button class="btn btn-dark">OUR SERVICES</button>
  <div class="grid lg:grid-cols-3 sm:grid-cols-2 gap-12">
    {#each services as { title, img }}
      <div class="flex items-center flex-col mt-[80px] text-center">
        <div
          class="bg-white w-[108px] h-[108px] flex justify-center items-center mb-[20px] rounded-full"
        >
          <img src={img} alt="" class="" />
        </div>
        <div
          class="font-bold text-[20px] leading-[24px] mb-[15px] tracking-[2px]"
        >
          {title}
        </div>
        <p class="mb-[20px] text-center">
          Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras
          ullamcorper bibendum bibendum. Duis tincidunt urna non pretium porta.
          Nam condimentum vitae ligula vel ornare.
        </p>
        <button
          class="border-[2px] border-white rounded-[30px] py-[20px] px-[34px] font-bold text-[14px] w-[165px]"
          >VIEW MORE</button
        >
      </div>
    {/each}
  </div>
  <div class="my-[120px] view-more">VIEW MORE DIGISALAD'S INGRADIENTS</div>
</div>
<div />
<div class="pr-[100px] bg-white relative">
  <div
    class="absolute rounded-ss-3xl top-0 bg-[#26C6D0] w-full h-[50%] rounded-ee-[25px]"
  />
  <div class="relative">
    <img
      src="/bg.png"
      class="absolute w-full h-full z-0 rounded-r-[25px] rounded-bl-[25px]"
      alt=""
    />
    <div class="relative z-1 flex py-[100px] justify-center max-lg:flex-col ">
      <div class="flex flex-col items-center text-white px-[25px]">
        <img
          src="/profile.png"
          class="rounded-full mb-[40px]"
          alt=""
          width="200"
          height="200"
        />
        <div
          class="text-center font-bold text-[20px] leading-[24px] tracking-[2px] mb-2"
        >
          Tony Ng
        </div>
        <div
          class="text-center font-normal italic text-[16px] leading-[16px] tracking-[2px]"
        >
          Founder & Creative Director
        </div>
      </div>
      <div
        class="max-w-[720px] font-bold tracking-[2px] p-4 leading-[48px] flex flex-col  justify-center items-center ml-4 text-white"
      >
      <img src="/quote.svg" class='mb-[25px]' alt="">
        <div class="tracking-[2px] font-bold">
          A great digital work isn't about designing beautiful pages purely. It
          is about context - how do we deliver the <span class="text-[#FFBC58]">
            experience to the right person at the right time</span
          >. The most important thing is that your work can engage customers at
          anytime, anywhere and let users experience an entire amazing digital
          journey.
        </div>
      </div>
    </div>
  </div>
</div>
<div class="flex flex-col items-center px-[200px] bg-white">
  <div
    class=" flex items-end font-bold text-[28px] mt-[125px] leading-9 decoration-wavy text-[#262626] underline decoration-[#26C6D0] underline-offset-8 p-2 tracking-[1px]"
  >
    <div>OUR BRAND EXPERIENCE</div>
    <div class="header" />
  </div>
  <p class="font-normal text-[16px] text-center mx-auto px-10 my-[30px]">
    Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras ullamcorper
    bibendum bibendum. Duis tincidunt urna non pretium porta. Nam condimentum
    vitae ligula vel ornare. Phasellus at semper turpis. Nunc eu tellus tortor.
    Etiam at condimentum nisl, vitae sagittis orci. Donec id dignissim nunc.
    Donec elit ante, eleifend a dolor et, venenatis facilisis dolor. In feugiat
    orci odio, sed lacinia sem elementum quis. Aliquam consectetur, eros et
    vulputate euismod, nunc leo tempor lacus, ac rhoncus neque eros nec lacus.
    Cras lobortis molestie faucibus.
  </p>
  <img src="/brand.png" alt="" />
</div>
<div class="relative">
  <img src="/showcase_bg.png" class="absolute w-full h-full z-0" alt="" />
</div>
<div class="relative">
  <img src="/bg_2.png" class="absolute w-full h-full z-0" alt="" />
  <div class="flex relative items-center justify-evenly z-1 w-full py-[200px]">
    <button
      class="bg-[#26C6D0] min-w-[50px] min-h-[50px] rounded-full flex items-center justify-center"
    >
      <img src="/left_chevron.svg" alt="" />
    </button>
    <div class="flex max-xl:flex-col mx-8 relative">
      <div class="absolute top-0 right-0 max-xl:translate-x-[100%] max-xl:translate-y-[-100%] text-white flex flex-col ">

        <div class='self-start'>01</div>
        <div class='pl-4 bg-[#26C6D0] min-w-[34px] min-h-[1px] rotate-[-45deg]'></div>
        <div class='self-end pl-6'>04</div>
      </div>
      <div class="relative">
        <img src="/case.png" class="rounded-[30px] w-full h-full object-fill block  max-xl:mb-[20px]" alt="" />
        <button class="btn absolute top-full translate-y-[-20%] max-xl:translate-y-[-60%] btn-md translate-x-[25%] right-0">VIEW PROJECT</button>
      </div>
      <div
        class="text-white ml-[30px] max-w-[450px] flex flex-col justify-center"
      >
        <div class="font-bold text-[16px] tracking-[2px] leading-[20px] mb-[20px]">

  HIGHLIGHTED SHOWCASE
</div>  
<div class="font-bold text-[32px] tracking-[3px] leading-[40px] mb-[40px] ">
  <div class='flex items-end'>
    <div class="title">

      LP CLUB MOBILE APP
    </div>
    <div class="header"/>
          </div>
        </div>
        <p class="text-[16px] tracking-[1px] font-normal leading-[24px]">
          Cras quis nulla commodo, aliquam lectus sed, blandit augue. Cras
          ullamcorper bibendum bibendum. Duis tincidunt urna non pretium porta.
          Nam condimentum vitae ligula vel ornare. Phasellus at semper turpis.
          Nunc eu tellus tortor. Etiam at condimentum nisl, vitae sagittis orci.
          Donec id dignissim nunc. Donec elit ante, eleifend a dolor et,
          venenatis facilisis dolor. In feugiat orci odio, sed lacinia sem
          elementum quis. Aliquam consectetur, eros et vulputate euismod, nunc
          leo tempor lacus, ac rhoncus neque eros nec lacus. Cras lobortis
          molestie faucibus.
        </p>
      </div>
    </div>
    <button
      class="bg-[#26C6D0] min-w-[50px] min-h-[50px] rounded-full flex items-center justify-center"
    >
      <img src="/right_chervon.svg" alt="" />
    </button>
  </div>
</div>

<style lang="scss">
  video {
    max-width: auto;
  }
  .bg {
    background: url("/bg.png");
    background-position: center;
    background-repeat: no-repeat;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 50px 150px;
    width: 100%;
  }
  .header {
    margin-left: 10px;
    margin-bottom: 8px;
    background-color: #ee6c8a;
    border-radius: 50%;
    height: 10px;
    width: 10px;
  }
  .btn {
    display: flex;
    align-items: center;
    background-color: #26c6d0;
    color: white;
    padding: 34px 24px;
    margin-bottom: 70px;
    font-weight: 700;
    line-height: 19px;
    &-md{
      @media not all and (min-width: 1280px) {
      padding: 17px 12px;
      }
    }

    &-dark {
      background-color: #585880;
    }
    &:after {
      content: "";
      margin-left: 14px;
      background-color: white;
      height: 2px;
      width: 50px;
    }

  }
  .view-more{
    position: relative;
    flex-direction: column;
    z-index: 1;
    &:after{
      content:'';
      z-index: -1;
      position:absolute;
      background-color:#FFBC58;
      height:10px;
      width:100%;
      bottom:0;
      left:0;
    }
  }
  .title{
    position: relative;
    z-index: 1;

    &:after{
      content:'';
      z-index: -1;
      position:absolute;
      background-color:#26C6D0;
      height:8px;
      width:100%;
      bottom:5px;
      left:0px;
    }
  }
</style>
