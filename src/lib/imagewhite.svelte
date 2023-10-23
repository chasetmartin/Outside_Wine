<script>
    import { fade } from 'svelte/transition';
    import { slide } from 'svelte/transition';
    import { blur } from 'svelte/transition';

    export let step;

    let media = [
        "/white1.jpg",
        "/white2.gif",
        "/white3.gif",
        "/red4.jpg",
        "/white5.gif",
        "/white6.gif",
        "/white7.gif",
        "/white8.jpg",
        "/red10.gif",
        "/white11.jpg"
    ];
</script>

{#key step}
<div class="text-center">
    <div class="rounded-lg mx-auto overflow-hidden opacity-80 w-9/12 h-auto" in:blur={{ duration: 800 }}>
        {#if step === 0 || step === 1 || step === 2 || step === 3 || step === 4 || step === 5 || step === 6 || step === 7 || step === 8 || step === 9}
            <img src={media[step]} alt="gif!" class="w-full" />
        {:else}
        <div></div>    
        {/if}
    </div>
</div>
{/key}


      
     
      
  