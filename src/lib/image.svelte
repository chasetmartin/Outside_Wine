<script>
    import { fade } from 'svelte/transition';
  
    export let step;
  
    let media = [
      "/red1.jpg",
      "/red2.mov",
      "/red3.jpg",
      "/red4.jpg",
      "/video1.mp4", // Add the path to your video file here
      "/video2.mp4", // Add more video paths if needed
    ];
</script>

{#key step}
<div class="text-center">
    <div class="rounded-lg mx-auto overflow-hidden opacity-80 w-11/12 h-auto">
        {#if step === 1}
            <video controls autoplay loop muted class="w-full">
                <source src={media[step]} type="video/mp4" />
                Your browser does not support the video tag.
            </video>
        {:else}
            <img src={media[step]} alt="grapes!" class="w-full" />
        {/if}
    </div>
</div>
{/key}

      
     
      
  