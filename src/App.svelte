<script lang="ts">
  import Component from "./lib/Component.svelte";
  import Counter from "./lib/Counter.svelte";

  let name = "paul";
</script>

<div class="container">
  <h1>My First Svelte Component</h1>

  <p>Hello World, My Name is {name}</p>

  <div>
    <a target="_blank" href="https://github.com/ipr0310" rel="noreferrer">
      Link to my Github Profile
    </a>
  </div>

  <div style="margin-top:2rem">
    <hr style="width:100%" />
  </div>

  <Component />
  <Counter />
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

  p {
    font-weight: 700;
    font-size: 2rem;
  }

  @keyframes zoom {
    0%,
    100% {
      transform: scale(0.5);
    }

    50% {
      transform: scale(1);
    }
  }
</style>
