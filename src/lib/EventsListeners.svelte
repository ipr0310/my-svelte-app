<script lang="ts">
  const onClick = () => {
    console.log("Clicked");
  };

  const showAlert = () => alert("Showing alert");
</script>

<h1 on:click|preventDefault|stopPropagation|once={onClick}>Event Listeners</h1>

<div
  on:click|self={() => {
    console.log("parent");
  }}
>
  parent

  <div
    on:click={() => {
      console.log("children");
    }}
  >
    children
  </div>

  <button on:click|once={showAlert}>
    Click me (Alert will be shown only once)</button
  >
</div>
