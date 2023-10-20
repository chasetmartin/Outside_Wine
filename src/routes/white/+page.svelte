<script>
    import { fade } from 'svelte/transition';
    import { goto } from '$app/navigation';

    import Scrolly from '../../lib/scrolly.svelte';
    import Imagewhite from '../../lib/imagewhite.svelte';
        
    let value;
    
    import { steps } from '../../lib/whitesteps.js';
</script>

<section in:fade={{ duration: 1000 }}>
    <div class="hero py-20 text-center">
        <h1 class="text-4xl font-bold">
          Let's make some white wine together!
        </h1>
        <h2 class="text-2xl font-light mt-4">
          I'll walk you through it step by step.
        </h2>
        <h3 class="text-xl text-gray-500 mt-4">
          Scroll Down to Begin
        </h3>
        <div class="p-4">
            <svg xmlns="http://www.w3.org/2000/svg" width="2em" height="2em" viewBox="0 0 24 24" {...$$props}><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 5v14m7-7l-7 7l-7-7"/></svg>
        </div>
    </div>

  <div class="section-container">
    <div class="steps-container">
      <Scrolly bind:value>
        {#each steps as text, i}
          <div class="step" class:active={value === i}>
            <div class="step-content w-4/5 p-6 border rounded shadow-xl transition duration-500 ease-in-out">{@html text}
              <svg class="m-4" xmlns="http://www.w3.org/2000/svg" width="0.8em" height="0.8em" viewBox="0 0 24 24" {...$$props}><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 5v14m7-7l-7 7l-7-7"/></svg>

            </div>
          </div>
        {/each}
        <div class="spacer" />
      </Scrolly>
    </div>
    <div class="sticky">
      <Imagewhite step={value} />
    </div>
  </div>
	<div class="hero py-20 text-center">
    <h1 class="text-3xl font-bold p-4">
      Thanks for letting me share my expertise and passion!
    </h1>
    <h2 class="text-2xl mt-4">
      <a href="https://chasethomasmartin.com/" target="_blank" class="text-blue-500 hover:underline">Chase Martin Dev</a> created October 2023 for Outside+
    </h2>
    <button class="border-black bg-slate-100 border rounded-md font-medium py-2 px-4 transition duration-300 ease-in-out transform hover:scale-105 mt-4 mx-6" on:click={() => goto("/")}>Return Home</button>
  </div>
</section>

<style>
	:global(body) {
		overflow-x: hidden;
	}
	
	.hero {
		height: 100vh;
		display: flex;
		place-items: center;
		flex-direction: column;
		justify-content: center;
		text-align: center;
	}
	
  .spacer {
    height: 40vh;
  }

  .sticky {
    position: sticky;
    top: 0;
		flex: 1 1 60%;
    width: 60%;
  }

  .section-container {
    margin-top: 1em;
    text-align: center;
    transition: background 100ms;
    display: flex;
  }

  .step {
    height: 80vh;
    display: flex;
    place-items: center;
    justify-content: center;
  }

  .step-content {
    font-size: 1.5rem;
    background: whitesmoke;
    color: #ccc;
  }

	.step.active .step-content {
		background: white;
		color: black;
	}
	
  .steps-container,
  .sticky {
    height: 100%;
    right: 0;
  }

  .steps-container {
    flex: 1 1 40%;
    z-index: 10;
  }

  svg {
  animation: pulse 2s infinite;
  }

@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
  }
	
/* Mobile text on top of images */
  @media screen and (max-width: 768px) {
    .section-container {
      flex-direction: column-reverse;
    }
    .sticky {
      width: 95%;
			margin: auto;
    }
  }
</style>
