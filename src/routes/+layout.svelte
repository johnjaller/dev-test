<script lang="ts">
  import "../app.css";
  import NavBar from "../lib/NavBar.svelte";
  import { setContext } from "svelte";
  let isNavbarSticky = false;
  setContext("isSticky", {
    isSticky: isNavbarSticky,
    setIsSticky: (isSticky: boolean) => (isNavbarSticky = isSticky),
  });
  let isSidebarOpen = false;

  $: scrollTop = 0;
  $: console.log(scrollTop);
  let videoContainerHeight: number;
</script>

<svelte:window bind:scrollY={scrollTop} />
<div class="bg-[#E5E5E5] relative tracking-[1px]">
  <div
    class="relative bg-white max-w-[100vw]"
    bind:offsetHeight={videoContainerHeight}
  >
    <video
      autoplay
      muted
      loop
      disablePictureInPicture
      class="w-full h-full rounded-b-[3%]"
      width="100%"
      height="100%"
    >
      <source src="/intro.mp4" type="video/mp4" />
    </video>
    <div
      class="absolute top-0 left-0 bg-[rgba(0,_0,_0,_0.3)] h-full w-screen rounded-b-[3%]"
    />
    <div
      class="absolute text-white rotate-[-90deg] flex side items-center  max-sm:hidden"
      style="left: -5%;
    top: 50%;"
    >
      DIGITAL AGENCY
    </div>
    <div
      class="absolute text-white max-sm:hidden"
      style="left: 15%;
            top: 25%;"
    >
      <img src="/icon_white.svg" class="mb-[34px]" alt="" />
      <div class="font-bold lg:text-[38px] text-white z-[2]">
        <div>WE CREATE</div>
        <div>AMAZING</div>
        <div class=" flex items-end">
          <div class="intro">DIGITAL EXPERIENCE</div>
          <div class="header" />
        </div>
      </div>
    </div>
    <div class="absolute bottom-6 left-1/2 translate-x-[-50%]">
      <button
        class="flex flex-col items-center text-white max-sm:hidden"
        on:click={() =>
          window.scrollTo({ top: videoContainerHeight, behavior: "smooth" })}
      >
        <img src="/salad.svg" alt="" />
        <div class="mt-[10px]">TASTE US NOW!</div>
      </button>
    </div>
    <div
      class="fixed top-0 z-20 left-0 px-[60px] py-[48px] h-screen w-screen overflow-y-auto transition-all {isSidebarOpen
        ? 'translate-x-0'
        : 'translate-x-[-100%]'}"
      style="background:  linear-gradient(180deg, #585880 3.61%, #26C6D0 95.7%); opacity:0.95;"
    >
      <nav class="flex justify-between items-start">
        <img src="/icon_white.svg" alt="" />
        <button
          class="w-[22px] h-[22px]"
          on:click={() => (isSidebarOpen = false)}
        >
          <img src="/close.svg" alt="" />
        </button>
      </nav>
      <div class="flex justify-between items-center max-md:flex-col max-md:gap-4">
        <div class="flex flex-col gap-4">
            <div
            class="relative rounded-[30px] w-[380px] h-[200px]"
          >
            <img
              src="/video-thumbnail.png"
              class="block w-full rounded-[30px] h-full object-cover"
              alt=""
            />
            <div
              class=" bg-[rgba(38,_198,_208,_0.9)] w-full h-full flex items-center justify-center absolute top-0 rounded-[30px] left-0 z-[2]"
            >
              <img src="/lettuce.svg" alt="" />
              <div class="flex flex-col ml-[30px] text-white">
                <div class="font-normal text-[16px]">EMPOWERING BRANDS</div>
                <div class="font-bold text-[32px] flex items-end">
                  <div>ABOUT US</div>
                  <div class="header header--menu" />
                </div>
              </div>
            </div>

           
          </div>
          <div class="relative rounded-[30px] w-[380px] max-h-[320px]">
            <img
              src="/menu_2.png"
              class="block w-full rounded-[30px] h-full object-cover"
              alt=""
            />
            <div
              class=" bg-[rgba(238,_108,_138,_0.9)] w-full h-full flex items-end justify-start absolute top-0 rounded-[30px] left-0 z-[2] pl-[35px] pb-[60px]"
            >
              <img src="/tomato.svg" alt="" />
              <div class="flex flex-col ml-[30px] text-white">
                <div class="font-normal text-[16px]">CASE STUDIES</div>
                <div class="font-bold text-[32px]">
                  <div class="flex items-end">
                    WORKS
                    <div class="header header--menu-blue" />
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
          <div class="flex flex-col gap-2">
            <div class="relative rounded-[30px] w-[290px]">
              <img
                src="/menu_3.png"
                class="block w-full rounded-[30px] h-full object-cover"
                alt=""
              />
              <div
                class=" bg-[rgba(230,_169,_78,_0.9)] w-full h-full flex items-start pb-[20px] pl-[20px] flex-col justify-end absolute top-0 rounded-[30px] left-0 z-[2]"
              >
                <img src="/cheese.svg" class="mb-[28px]" alt="" />
                <div class="flex flex-col text-white">
                  <div class="font-normal text-[16px]">BE COOL WITH US</div>
                  <div class="font-bold text-[32px] flex items-end">
                    <div>CAREERS</div>
                    <div class="header header--menu" />
                  </div>
                </div>
              </div>
            </div>
            <div class="relative rounded-[30px] w-[290px] max-h-[430px]">
                <img
                src="/menu_4.png"
                class="block w-full rounded-[30px] h-full"
                alt=""
                />
                <div
                class=" bg-[rgba(38,_208,_168,_1)] w-full h-full flex items-start pb-[20px] pl-[20px] flex-col justify-end absolute top-0 rounded-[30px] left-0 z-[2]"
                >
                <img src="/cucumber.svg" alt="" />
                <div class="flex flex-col text-white">
                    <div class="font-normal text-[16px]">OUR STRATEGIES</div>
                    <div class="font-bold text-[32px] flex items-end">
                        <div>INSIGHTS</div>
                        <div class="header header--menu" />
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="flex flex-col gap-4">
        <div class="relative rounded-[30px] w-[290px] max-h-[430px]">
          <img
            src="/menu_5.png"
            class="block w-full rounded-[30px] h-full"
            alt=""
          />
          <div
            class=" bg-[rgba(88,_88,_128,_0.9)] w-full h-full flex items-start pb-[20px] pl-[20px] flex-col justify-end absolute top-0 rounded-[30px] left-0 z-[2]"
          >
            <img src="/carrot.svg" alt="" />
            <div class="flex flex-col text-white">
              <div class="font-normal text-[16px]">AREAS OF EXPERTISE</div>
              <div class="font-bold text-[32px] flex items-end">
                <div>SERVICES</div>
                <div class="header header--menu" />
              </div>
            </div>
          </div>
        </div>
        <div
          class="bg-white rounded-[30px] w-[290px] max-h-[430px] flex flex-col text-dark items-start p-4 justify-center"
        >
          <div class="font-normal text-[16px] leading-[20px] tracking-[2px]">
            START YOUR JOURNEY WITH US
          </div>
          <div class="flex flex-col text-[#26C6D0]">
            <div class="font-normal text-[16px]">CONTACT</div>
            <div class="font-bold text-[32px] flex items-end">
              <div>SERVICES</div>
              <div class="header header--menu" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
      <!-- <div class="flex items-center">
            <img src="/tomato.svg" alt="">
        </div> -->

  <NavBar
    isSticky={scrollTop > videoContainerHeight - 100}
    on:menuClick={() => (isSidebarOpen = !isSidebarOpen)}
  />
  <slot />
</div>

<style lang="scss">
  .bg-thumbnail {
    position: absolute;
    top: 0;
    left: 0;
    background-image: url("/video-thumbnail.png");
    background-position: center;
    background-size: cover;
    width: 100%;
    height: 100%;
    opacity: 1;
  }
  .side {
    &::before {
      content: "";
      height: 2px;
      width: 100px;
      background-color: white;
      margin-right: 25px;
    }
  }
  .header {
    margin-left: 10px;
    background-color: #ee6c8a;
    margin-bottom: 18px;
    border-radius: 50%;
    height: 10px;
    width: 10px;
    &--menu {
      margin-bottom: 8px;
    }
    &--menu-blue {
      margin-bottom: 8px;
      background-color: #26c6d0;
    }
  }
  .intro {
    position: relative;
    z-index: 1;

    &:after {
      content: "";
      z-index: -1;
      position: absolute;
      background-color: #26c6d0;
      height: 8px;
      width: 100%;
      bottom: 10px;
      left: 0;
    }
  }
</style>
