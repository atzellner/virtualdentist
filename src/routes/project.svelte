<svelte:head>
        <title>Project</title>
</svelte:head>

<script>
            import { fly } from 'svelte/transition';

    $: o = 0;
    let oldproject = ["image3.png", "image40.png", "image43.png"];

    $: g = 0;

    let goals = ["image4.jpeg", "image39.png"];

    $: e = 0;

    let examroom = ["image15.png","image16.jpeg", "image17.png", "image18.png", "image22.jpeg"];

    $: p = 0;

    let patient = ["image41.png", "image42.png", "image28.png", "image29.jpeg"];

    import { onDestroy } from 'svelte';

 function onInterval(callback, milliseconds) {
	const interval = setInterval(callback, milliseconds);

	onDestroy(() => {
		clearInterval(interval);
	});
}

	onInterval(updateImg, 3000);

    function updateImg(){
        if(o < oldproject.length - 1 ) {
            o++;
        } else {
            o = 0;
        }

        if(g < goals.length - 1 ) {
            g++;
        } else {
            g = 0;
        }

        if(e < examroom.length - 1 ) {
            e++;
        } else {
            e = 0;
        }

        if(p < patient.length - 1 ) {
            p++;
        } else {
            p = 0;
        }
    }

</script>
<div  in:fly="{{ y: -50, duration: 250, delay: 300 }}"
out:fly="{{ y: -50, duration: 250 }}">


<section>
    <div class="imgslider">
        <img class="generic"  src="/img/media/{oldproject[o]}" alt="">
    </div>
<div class="sectioncont" >
    <h3>What is Virtual Dentist?</h3>
<p>
    Virtual Dentist simulates a dental surgery environment, in which users can practice caries removal inside VR using a haptic device to control the handpiece. 
</p>
</div>
   
</section>
<section >
    <div class="imgslider">
            <img  class="generic" src="/img/media/{goals[g]}" alt="">

    </div>
    <div class="sectioncont">
         <h3>Semester Project</h3>   
    <p>The starting point for the semester project was a fully functional simulation, which, however, was kept visually rather minimalistic. 
        The goal of our working group was to graphically enhance the existing simulation. The treatment room and the patient should look more realistic.
        Therefore, we spent two days in a dentist's office and examined it in detail. We collected as much material as possible to implement a realistic treatment room inside the simulation. Special thanks go to the oral and maxillofacial surgical practice Sternklinik in Bremen, which had made these visits possible. </p>

    </div>
   </section>
<section > 
  <div class="imgslider">
<img class="generic"  src="/img/media/{examroom[e]}" alt="">
  </div>  
    <div class="sectioncont">
      <h3>Exam Room</h3>
   <p>We first developed a floor plan for the new treatment room based on the experience gained in the Sternklinik.
    The necessary models were created in Blender. We were able to use a few images from the clinic for textures. 
    Our models were merged into the room in the Unreal Engine.   
</p>  
    </div>
   

</section>

<section >
    <div class="imgslider">
            <img  class="generic"  src="/img/media/{patient[p]}" alt="">

    </div> 

    
      


    <div class="sectioncont">
         <h3>Patient</h3> 
    <p>We resorted to Epic Games MetaHuman Creator to have the most realistic patient possible. A tooth was removed from our created patient so that we could place the drillable tooth. Finally, the patient was placed in the room and animated.</p>

    </div>
   </section>
   
<div> 
    <div class="sectioncont center">
           <h3>Documentary</h3> 
    
    </div>
</div>

</div>