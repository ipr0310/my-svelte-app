<script lang="ts">
  import SvelteLogo from "./assets/svelte-logo-horizontal.svg";
  import Divider from "./lib/Divider.svelte";
  import Counter from "./lib/Counter.svelte";
  import Component from "./lib/Component.svelte";
  import EventsListeners from "./lib/EventsListeners.svelte";

  let name = "Paul";

  const changeName = () => {
    name = name === "Paul" ? "Paola" : "Paul";
  };
</script>

<main class="container">
  <a
    href="https://svelte.dev"
    target="_blank"
    rel="noreferrer"
    style="align-self: center;"
  >
    <img src={SvelteLogo} class="logo svelte" alt="Svelte Logo" />
  </a>

  <h1>My First Svelte Component</h1>

  <p>Hello World, My Name is {name}</p>

  <button on:click={changeName}>Change Name</button>

  <Counter />

  <Divider />

  <Component />

  <Divider />

  <EventsListeners />
</main>

<style>
  .container {
    display: flex;
    flex-direction: column;
  }

  h1 {
    color: purple;
    font-size: 4rem;
    margin-bottom: 0;
    animation: zoom 2s infinite;
  }

  p {
    font-weight: 700;
    font-size: 2rem;
  }

  @keyframes -global-zoom {
    0%,
    100% {
      transform: scale(0.5);
    }

    50% {
      transform: scale(1);
    }
  }
</style>
