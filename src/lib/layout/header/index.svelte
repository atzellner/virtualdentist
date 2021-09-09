<script>
  import Logo from '$lib/layout/logo/index.svelte';
  let menuvisible = false;

    function openMenu() {
        menuvisible = !menuvisible;
    }
    function closeMenu() {
        menuvisible = false;
    }

</script>
<header>
  <a sveltekit:prefetch class="homelogo" href="/">
    <Logo />    
  </a>

  <div class="burgermenu" on:click={openMenu}>
    <span class="outerspan">
        <span class="innerspan"></span>
    </span>
    <span class="outerspan">
        <span class="innerspan"></span>
    </span>
  </div>
{#if menuvisible}
  <div class="mobile" >
    <div> 
      <a href="project" on:click={closeMenu}>Project</a>
    <a href="team" on:click={closeMenu}>Team</a>
    <a href="https://cgvr.cs.uni-bremen.de/contact/" on:click={closeMenu}>Contact Us</a>
    </div>
    
  </div>
{/if}
  <nav>
    <a href="project">Project</a>
    <a href="team">Team</a>
    <a href="https://cgvr.cs.uni-bremen.de/contact/">Contact Us</a>
  </nav>

</header>
