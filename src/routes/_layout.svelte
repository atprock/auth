<script>
  // Importing modules
  import { onMount } from "svelte";
  
  let loaded = false;
  
  onMount(() => {
    setTimeout(() => loaded = true, 1000);
  });
</script>

<!-- Loading screen  -->
{ #if !loaded }
  <div style="z-index: 999;" class="fixed w-full h-screen flex justify-center items-center bg-white">
    <p>Loading</p>
  </div>
<!-- Layout -->
{ :else }
  <main>
    <slot />
  </main>
{ /if }