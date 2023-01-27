<script lang="ts">
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher<{
    myEvent: { text: string };
  }>();

  const sayHello = () => {
    dispatch("myEvent", {
      text: "Hello World, This is my Event!",
    });
  };

  // Second Example
  //   const dispatch = createEventDispatcher<{ select: Date }>();
  //   dispatch("select", date);
</script>

<h1>Component Events</h1>

<button on:click={sayHello}> Click to say hello </button>
