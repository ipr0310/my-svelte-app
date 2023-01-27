<script lang="ts">
  import SvelteLogo from "./assets/svelte-logo-horizontal.svg";
  import Divider from "./lib/Divider.svelte";
  import Counter from "./lib/Counter.svelte";
  import Component from "./lib/Component.svelte";
  import EventsListeners from "./lib/EventsListeners.svelte";
  import ReactiveDeclarations from "./lib/ReactiveDeclarations.svelte";
  import ComponentProps from "./lib/ComponentProps.svelte";
  import ConditionalRendering from "./lib/ConditionalRendering.svelte";
  import LoopRendering from "./lib/LoopRendering.svelte";
  import AwaitBlocks from "./lib/AwaitBlocks.svelte";
  import DomEvents from "./lib/DomEvents.svelte";
  import ComponentEvents from "./lib/ComponentEvents.svelte";

  const componentProps = {
    name: "Uchiha Madara",
    answer: 65,
  };

  const handleMessage = (event: CustomEvent<{ text: string }>) => {
    alert(event.detail.text);
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

  <Counter />

  <Divider />

  <Component />

  <Divider />

  <EventsListeners />

  <Divider />

  <ReactiveDeclarations />

  <Divider />

  <ComponentProps {...componentProps} />

  <Divider />

  <ConditionalRendering />

  <Divider />

  <LoopRendering />

  <Divider />

  <AwaitBlocks />

  <Divider />

  <DomEvents />

  <Divider />

  <ComponentEvents on:myEvent={handleMessage} />

  <Divider />
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
