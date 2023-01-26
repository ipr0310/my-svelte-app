<script lang="ts">
  const onClick = () => {
    console.log("Clicked");
  };
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
</div>
