<script lang="ts">
  let name = "Naruto";

  let a = 1;
  let b = 2;

  let active = false;
</script>

<h1>Text Inputs</h1>

<label>
  <input bind:value={name} style="margin-bottom:1em" />
  <span>Hello {name}</span>
</label>

<label>
  A
  <input type="number" bind:value={a} min="0" max="10" />
  <input type="range" bind:value={a} min="0" max="10" />
</label>

<label style="margin:1em 0">
  B
  <input type="number" bind:value={b} min="0" max="10" />
  <input type="range" bind:value={b} min="0" max="10" />
</label>

<p>{a} + {b} = {a + b}</p>

<label>
  <input type="checkbox" bind:checked={active} />
  Yes! Send me regular email spam
</label>

{#if active}
  <p>Thank you. We will bombard your inbox and sell your personal details.</p>
{:else}
  <p>You must opt in to continue. If you're not paying, you're the product</p>
{/if}

<button disabled={!active}> Subscribe </button>
