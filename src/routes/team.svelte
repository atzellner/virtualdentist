<script>
            import { fly } from 'svelte/transition';
</script>
<svelte:head>
        <title>Team</title>
</svelte:head>
<div  in:fly="{{ y: -50, duration: 250, delay: 300 }}"
out:fly="{{ y: -50, duration: 250 }}">

<h1 class="center">Team</h1>
<section class="center firstteam"> <div>
     <h3 >Management</h3>
   <p>Prof. Dr. Gabriel Zachmann</p> 
    <p>Dr. René Weller</p> 
    <p>Prof. Dr. Peter Haddawy</p>
    <p>  M.Sc. Maximilian Kaluschke</p></div>
</section>

   

<img  class="group" src="/img/gruppe.jpg" alt="group picture" style="">

<section>

    <div class="center">
          <h3>Students</h3>

   <p>Philipp Camphausen</p> 
    <p>Sandra Grisko</p> 
    <p>Leon Sippel</p>  
    <p>Hannes Wattenberg</p> 
    <p>Aaron Zellner</p>   
    </div>

</section>

</div>
