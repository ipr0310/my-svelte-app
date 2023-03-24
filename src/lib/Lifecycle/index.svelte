<script>
  import { onMount, tick } from "svelte";
  import Timer from "./Timer.svelte";

  //   On Mount
  let photos = [];
  //   onMount(async () => {
  //     const res = await fetch("https://svelte.dev/tutorial/api/album");
  //     photos = await res.json();
  //   });

  // On Destroy
  let open = true;
  let seconds = 0;

  const toggle = () => (open = !open);
  const handleTick = () => (seconds += 1);

  // Tick
  let count = 1;
  $: double = count * 2;

  const increment = async () => {
    count++;
    // double is still 2

    await tick();

    // 🎉 double is now 4!
    console.log(double); // 4
  };
</script>

<h1>Component Lifecycle</h1>

<h2>On Mount</h2>

<div class="photos">
  {#each photos as photo}
    <figure>
      <img src={photo.thumbnailUrl} alt={photo.title} />
      <figcaption>{photo.title}</figcaption>
    </figure>
  {:else}
    <!-- this block renders when photos.length === 0 -->
    <p>loading... (Data will not load due to CORS rules)</p>
  {/each}
</div>

<h2>On Destroy</h2>

<button on:click={toggle}>{open ? "Close" : "Open"} Timer</button>
<p>
  The Timer component has been open for
  {seconds}
  {seconds === 1 ? "second" : "seconds"}
</p>

{#if open}
  <Timer callback={handleTick} />
{/if}

<h2>Tick</h2>
<button on:click={increment}>Increment count</button>
<p>
  Count is {count}
  <br />
  Current count multiplied by 2 is {double}
</p>
