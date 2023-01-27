<script lang="ts">
  const getRandomNumber = async () => {
    const res = await fetch(`https://svelte.dev/tutorial/random-number`);
    const text = await res.text();

    if (res.ok) return text;

    throw new Error(text);
  };

  let promise = getRandomNumber();

  const handleClick = () => (promise = getRandomNumber());
</script>

<h1>Await Blocks</h1>

<button on:click={handleClick}> Generate random number </button>

{#await promise}
  <p>Waiting...</p>
{:then number}
  <p>The number is {number}</p>
{:catch error}
  <p style="color: red">{error.message}</p>
{/await}
