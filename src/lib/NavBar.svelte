<script lang='ts'>
      import IntersectionObserver from "./IntersectionObserver.svelte";
  import { createEventDispatcher } from "svelte";
  const dispatch=createEventDispatcher()
export let isSticky=false
</script>

<nav class="{isSticky?'fixed top-0 w-screen bg-white opacity-90 nav':'absolute w-screen'}  flex justify-between top-0 bg-transparent z-10 px-[60px] py-[40px]">
    {#if isSticky}
 <img src="/icon.svg" alt="">
 {:else}
 <img src="/icon.svg" class="max-sm:visible invisible" alt="">
 {/if}
 <div class="flex items-center">
    <button class="nav-btn max-md:hidden">START YOUR PROJECT</button>
    <button on:click={()=>dispatch('menuClick')}> <img src={isSticky?"/menu_dark.svg":"/menu.svg"} width="30" height="30" alt=""></button>
 </div>
</nav>

<style lang='scss'>
    @keyframes fadeIn {
        0%{
            opacity:0;
            transform: translateY(-100%);
        }
        100%{
            opacity: 0.9;
            transform: translateY(0);

        }
    }
    .nav{
        animation: fadeIn 0.8s ease-out 0s ;
    }
    .nav-reverese{
        animation: fadeIn 0.5s ease 0s ;
        animation-direction: reverse;
    }
    .nav-btn{
        background: linear-gradient(90deg, #4EE5EA 3.94%, #26D0A8 94.73%);
        color: white;
        border-radius: 24px;
        margin-right: 44px;
        font-weight: 700;
        font-size: 14px;
        line-height: 18px;
        padding: 12px 10px;
    }
</style>