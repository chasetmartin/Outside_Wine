<script>
  import { onMount } from 'svelte';
  import { currentStep } from '$lib/store';

  let localStep = 1; // A local variable specific to this component

  onMount(() => {
    const stepElements = document.querySelectorAll('.step-trigger');

    const observer = new IntersectionObserver((entries) => {
      if (entries[0].isIntersecting) {
        currentStep.update((step) => step + 1);
      }
    });

    stepElements.forEach((stepElement) => {
      observer.observe(stepElement);
    });

    return () => {
      observer.disconnect();
    };
  });
</script>

<main>
  <div class="step-content">
    <h2>Step {$currentStep}: Your content here</h2>
    <p>Content specific to this step.</p>
  </div>
  <div class="step-trigger">
    <button on:click={() => currentStep.update((step) => step + 1)}>Next Step</button>
  </div>
</main>

<style>
  .step-content {
       height: 110vh;
       display: flex;
       align-items: center;
       justify-content: center;
     }
 </style>