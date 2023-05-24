<script>
  import { onMount } from 'svelte';
  import Loading from './Loading.svelte';
  import Header from './Header.svelte';
  import Footer from './Footer.svelte';

  let isLoading = true;

  onMount(() => {
    if (document.readyState === 'complete') {
      setTimeout(setIsLoading, 3000); // Set isLoading to false if the page has already finished loading
    } else {
      window.addEventListener('load', () => {
        isLoading = false; // Set isLoading to false when the page has finished loading
      });
    }

    function setIsLoading() {
      isLoading = false;
    }
  });
</script>

{#if isLoading}
  <Loading/>
{:else}
  <div class="mainpage min-h-screen">
    <div id="landingpage" class="flex flex-col z-50">
      <Header />
      <div class="flex flex-col items-center justify-center flex-1">
        <img class="grey-image w-[30vw] absolute" src="nah-logo.png" alt="background" draggable="false" />
        <div class="flex flex-col items-center justify-center gap-[20px]">
          <h1 class="text-white text-[60px] z-10">NO ALPHA HERE</h1>
          <button class="bg-white w-[200px] h-[50px] z-10">MINT NOW</button>
        </div>
      </div>
    </div>
    <p class="text-white text-center">Explore the NAHVERSE</p>
    <Footer />
  </div>
{/if}

<style>
#landingpage {
    background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('/nah-bg.jpeg');
    min-height: 95vh;
    height: 100%;
    background-position: center;
    background-size: cover;
  }

  .grey-image {
    filter: grayscale(100%) brightness(7%);
  }
</style>