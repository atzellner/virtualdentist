
<svelte:head>
        <title>Virtual Dentist</title>
</svelte:head>

<script>
       import { fly } from 'svelte/transition';

let array = ["tooth_00000.jpg", "tooth_00001.jpg", "tooth_00002.jpg", "tooth_00003.jpg", "tooth_00004.jpg", "tooth_00005.jpg", "tooth_00006.jpg", "tooth_00007.jpg", 
"tooth_00008.jpg", "tooth_00009.jpg", "tooth_00010.jpg", "tooth_00011.jpg", "tooth_00012.jpg", "tooth_00013.jpg"];
let m = { x: 0, y: 0 };
$: v = 0;
$:n=0;
$: x = 0;

function handleMousemove(event) {
    m.x = event.clientX;
    m.y = event.clientY;
    v = m.x/w;
    n = Math.round(v*array.length);
}

$: w = 0;

$: safeValue = clamp(0, array.length-1, n);

const clamp = (min, max, v) => {
    if (v <= min) {
      return min;
    }
    if (v >= max) {
      return max;
    }

    return v;
  }

</script>

<div class="dentisthome"  bind:clientWidth={w} on:mousemove={handleMousemove}  in:fly="{{ y: -50, duration: 250, delay: 300 }}"
out:fly="{{ y: -50, duration: 250 }}">
<div class="herotooth" >
  
<img src="/img/tooth/{array[safeValue]}" alt="rendering of a tooth">

</div>

<div>
<h1 class="homeheader">practice caries removal <br> in virtual reality</h1>
<p class="bp"> Virtual Dentist allows dental students to gain important dental drilling experience that they would otherwise be denied during their studies. </p>
<a class="button" href="project">Learn more</a>
</div>

</div>
