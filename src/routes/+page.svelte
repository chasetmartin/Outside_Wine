<script>
    import { fade } from 'svelte/transition';
    import { goto } from '$app/navigation';
  
    let showStory = false;
  
    function startStory() {
      goto('/red');
    }
  </script>
  
  <main>
    
    <section>
        <div class="hero py-20 text-center">
          <h1 class="hero-content text-4xl font-bold">
            Let's make wine together!
          </h1>
          <h2 class="text-2xl font-light mt-4">
            What kind of wine would you like to make today?
          </h2>
          <button class="border-black bg-red-700 border text-white rounded-md font-medium py-2 px-4 transition duration-300 ease-in-out transform hover:scale-105 mt-4 mx-6" on:click={startStory}>Red</button>
          <button class="border-black bg-yellow-100 border rounded-md font-medium py-2 px-4 transition duration-300 ease-in-out transform hover:scale-105 mt-4 mx-6" on:click={startStory}>White</button>
          <p class="p-6 m-10 border rounded-xl">
            I built this storytelling app for a job application to <strong>Outside+</strong> to demonstrate my ability to explain a complex process in which I have expertise.
          </p>
        </div>
        <div></div>
      </section>
      
   
  </main>
  
  <style>
	.hero {
		height: 100vh;
		display: flex;
		place-items: center;
		flex-direction: column;
		justify-content: center;
		text-align: center;
	}
  
    .hero-content {
      text-align: center;
    }
  </style>