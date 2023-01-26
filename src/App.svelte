<script lang="ts">
  import Component from "./lib/Component.svelte";
  import Counter from "./lib/Counter.svelte";
  import SvelteLogo from "./assets/svelte-logo-horizontal.svg";

  let name = "Paul";

  const changeName = () => {
    name = name === "Paul" ? "Paola" : "Paul";
  };
</script>

<div class="container">
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

  <div>
    <a target="_blank" href="https://github.com/ipr0310" rel="noreferrer">
      Link to my Github Profile
    </a>
  </div>

  <div>
    <hr style="width:100%" />
  </div>

  <Component />
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
  }

  :global(h1) {
    color: purple;
    font-size: 4rem;
    margin-bottom: 0;
    animation: zoom 2s infinite;
  }

  :global(p) {
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
