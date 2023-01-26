<script lang="ts">
  let count = 0;

  const increment = () => {
    count++;
  };
</script>

<button on:click={increment} style="margin:1rem 0">
  Count is {count}
</button>
