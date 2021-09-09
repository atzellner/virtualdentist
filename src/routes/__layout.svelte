<script>
     import { onMount } from 'svelte';
     let dis = false;

     onMount(async () => {
    dis = true;
  });

    import Header from '$lib/layout/header/index.svelte';
    import Footer from '$lib/layout/footer/index.svelte';
 
</script>
<Header />

{#if dis}
<div class="dentin"  >
    <slot></slot>
</div>
{/if}
<Footer />