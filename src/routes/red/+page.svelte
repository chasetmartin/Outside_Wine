<script>
    import { fade } from 'svelte/transition';

    import Scrolly from '../../lib/scrolly.svelte';
    import Image from '../../lib/image.svelte';
        
    let value;
    
    import { steps } from '../../lib/redsteps.js';
</script>

<section transition:fade={{ duration: 1000 }}>
    <div class="hero py-20 text-center">
        <h1 class="text-4xl font-bold">
          Let's make some red wine together!
        </h1>
        <h2 class="text-2xl font-light mt-4">
          I'll walk you through it step by step.
        </h2>
        <h3 class="text-xl text-gray-500 mt-4">
          Scroll Down to Begin
        </h3>
      </div>

  <div class="section-container">
    <div class="steps-container">
      <Scrolly bind:value>
        {#each steps as text, i}
          <div class="step" class:active={value === i}>
            <div class="step-content w-4/5 p-6 border rounded shadow-xl transition duration-500 ease-in-out">{@html text}</div>
          </div>
        {/each}
        <div class="spacer" />
      </Scrolly>
    </div>
    <div class="sticky">
      <Image step={value} />
    </div>
  </div>
	<div class="hero py-20 text-center">
    <h1 class="text-3xl font-bold p-4">
      Thanks for letting me share my expertise and passion!
    </h1>
    <h2 class="text-2xl mt-4">
      <a href="https://chasethomasmartin.com/" target="_blank" class="text-blue-500 hover:underline">Chase Martin Dev</a> created on 10/19/23 for Outside+
    </h2>
  </div>
</section>

<style>
	:global(body) {
		overflow-x: hidden;
	}
	
	.hero {
		height: 80vh;
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
    top: 10%;
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
    /* font-size: 1rem; */
    background: whitesmoke;
    color: #ccc;
    /* border-radius: 5px;
    padding: .5rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: center; */
    /* transition: background 500ms ease;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, .2);
    text-align: left;
		width: 75%;
		margin: auto;
		max-width: 500px; */
  }


	.step.active .step-content {
		background: white;
		color: black;
	}
	
  .steps-container,
  .sticky {
    height: 100%;
  }

  .steps-container {
    flex: 1 1 40%;
    z-index: 10;
  }
	
/* Comment out the following line to always make it 'text-on-top' */
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
