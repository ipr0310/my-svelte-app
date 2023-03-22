<script lang="ts">
  const onClick = () => {
    console.log("Clicked");
  };

  const showAlert = () => alert("Showing alert");
</script>

<button on:click|preventDefault|stopPropagation|once={onClick}>
  Event Listeners
</button>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div
  style="padding:1rem"
  on:click|self={() => {
    console.log("parent");
  }}
>
  parent

  <button
    style="margin:1rem 0"
    on:click={() => {
      console.log("children");
    }}
  >
    children
  </button>

  <button on:click|once={showAlert}>
    Click me (Alert will be shown only once)
  </button>
</div>
