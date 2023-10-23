<script>
    import { fade } from 'svelte/transition';
    import { slide } from 'svelte/transition';
    import { blur } from 'svelte/transition';

    export let step;

    let media = [
        "/white1.jpg",
        "/white2.mov",
        "/white3.mov",
        "/red4.jpg",
        "/white5.mov",
        "/white6.mov",
        "/white7.mov",
        "/white8.jpg",
        "/red10.mov",
        "/white11.jpg"
    ];
</script>

{#key step}
<div class="text-center">
    <div class="rounded-lg mx-auto overflow-hidden opacity-80 w-9/12 h-auto" in:blur={{ duration: 800 }}>
        {#if step === 1 || step === 2 || step === 4 || step === 5 || step === 6 || step === 8}
            <video controls autoplay muted playsinline loop class="w-full">
                <source src={media[step]} type="video/mp4" />
                Your browser does not support the video tag.
            </video>
        {:else if step === 0 || step === 3 || step === 7 || step === 9}
            <img src={media[step]} alt="grapes!" class="w-full" />
        {:else}
        <div></div>    
        {/if}
    </div>
</div>
{/key}


      
     
      
  