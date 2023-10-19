<script>
    import { fade } from 'svelte/transition';
    import { goto } from '$app/navigation';
  
    let showStory = false;
  
    function startStory() {
      goto('/red');
    }
</script>
  
<main class="flex items-center justify-center h-screen">
  <section>
    <div class="hero py-10 text-center bg-slate-100 items-center w-4/5 mx-auto border border-black rounded-3xl">
      <h1 class="hero-content text-4xl font-bold">
        I hear <span class="text-yellow-500">Outside</span> is looking to start their own wine label...
      </h1>
      <h2 class="text-2xl font-light mt-4">
        What kind of wine would you like to make today?
      </h2>
      <button class="border-black bg-red-700 border text-white rounded-md font-medium py-2 px-4 transition duration-300 ease-in-out transform hover:scale-105 mt-4 mx-6" on:click={startStory}>Red</button>
      <button class="border-black bg-yellow-100 border rounded-md font-medium py-2 px-4 transition duration-300 ease-in-out transform hover:scale-105 mt-4 mx-6" on:click={startStory}>White</button>
      <p class="p-6 m-10 border border-black rounded-xl mx-auto w-3/5 text-center">
        I built this storytelling app for a job application to <strong>Outside Interactive Inc.</strong> to demonstrate my ability to explain a complex process in which I have expertise (winemaking), and to highlight my programming skills.
      </p>
      <p>
        October 2023 
      </p>
      <a class="text-blue-500 hover:underline" href="https://chasethomasmartin.com">chasethomasmartin.com</a>
    </div>
    <div class="hero-overlay"></div>
  </section>
</main>
  
<style>
  .hero {
    text-align: center;
    position: relative;
  }

  .hero-overlay {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-image: url('/vineyard.jpg');
    background-size: cover;
    opacity: 0.25;
   filter: blur(1px);
    z-index: -1;
  }
  
  .hero-content {
    text-align: center;
    z-index: 1;
  }
</style>
