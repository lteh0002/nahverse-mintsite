<script>
  import { onMount } from 'svelte';
  import Loading from './Loading.svelte';
  import Header from './Header.svelte';
  import Footer from './Footer.svelte';

  let isLoading = true;

  onMount(() => {
    setTimeout(loading, 3000);
    function loading() {
      if (document.readyState === 'complete') {
      isLoading = false; // Set isLoading to false if the page has already finished loading
    }
    }
  });
</script>

{#if isLoading}
  <Loading/>
{:else}
  <div class="mainpage min-h-screen">
    <Header class='Header'/>
    <div class="flex flex-col items-center justify-center flex-1 relative z-20">
      <div class="relative mt-[20%] z-10 flex flex-col justify-center items-center gap-[20px]">
        <h1 class="text-white text-[60px] z-10">NO ALPHA HERE</h1>
        <button class="bg-white w-[200px] h-[50px] z-10">MINT NOW</button>
        <img class="absolute w-[30vw] grey-image z-0" src="nah-logo.png" alt="background" draggable="false" />
      </div>
      <p class="text-white mt-[16%]">Explore the NAHVERSE</p>
    </div>
    <Footer />
  </div>
{/if}

<style>
  .mainpage {
    background-image: url('/nah-bg.jpeg');
    min-height: 100vh;
    height: 100%;
    background-position: center;
    background-size: cover;
  }

  .grey-image {
    filter: grayscale(100%) brightness(7%);
  }
</style>