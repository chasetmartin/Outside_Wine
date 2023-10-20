<script>
    import { fade } from 'svelte/transition';
    import { slide } from 'svelte/transition';
    import { blur } from 'svelte/transition';

    export let step;

    let media = [
        "/red1.jpg",
        "/red2.mov",
        "/red3.mov",
        "/red4.jpg",
        "/red5.jpg",
        "/red6.mov",
        "/red7.jpg",
        "/red8.mov",
        "/red9.mov",
        "/red10.mov",
        "/red11.jpg"
    ];
</script>

{#key step}
<div class="text-center">
    <div class="rounded-lg mx-auto overflow-hidden opacity-80 w-9/12 h-auto" in:blur={{ duration: 800 }}>
        {#if step === 1 || step === 2 || step === 5 || step === 7 || step === 8 || step === 9}
            <video controls autoplay loop muted class="w-full">
                <source src={media[step]} type="video/mp4" />
                Your browser does not support the video tag.
            </video>
        {:else if step === 0 || step === 3 || step === 4 || step === 6 || step === 10}
            <img src={media[step]} alt="grapes!" class="w-full" />
        {:else}
        <div></div>    
        {/if}
    </div>
</div>
{/key}


      
     
      
  