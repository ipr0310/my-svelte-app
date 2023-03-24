<script>
  import { onDestroy } from "svelte";

  export let callback;
  export let frequency = 1000;

  const interval = setInterval(callback, frequency);

  onDestroy(() => {
    clearInterval(interval);
  });
</script>

<p>
  This component executes a callback every
  {interval} millisecond{frequency === 1 ? "" : "s"}
</p>

<style>
  p {
    border: 1px solid blue;
    padding: 5px;
  }
</style>
