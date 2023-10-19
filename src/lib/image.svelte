<script>
    import { fade } from 'svelte/transition';
  
    export let step;
  
    let textContent = [
      "Step 1: Introduction",
      "Step 2: Process",
      "Step 3: Conclusion",
      "Step 4: Resources"
      // Add more text as needed
    ];
  </script>
  
  {#key step}
  <p in:fade={{duration: 500}} class="text-2xl font-bold">
    {textContent[step]}
  </p>
    {/key}
  