<script>
  import { onMount } from 'svelte';
  import Loading from './Loading.svelte';

  let isLoading = true;

  onMount(() => {
    if (document.readyState === 'complete') {
      isLoading = false; // Set isLoading to false if the page has already finished loading
    } else {
      window.addEventListener('load', () => {
        isLoading = false; // Set isLoading to false when the page has finished loading
      });
    }
  });
</script>

{#if isLoading}
  <Loading/>
{:else}
  <div>
    
  </div>
{/if}