<script lang="ts">
  let obj = { count: 0, randomInt: 0 };

  const increment = () => {
    obj.count++;
  };

  const doSomethingElse = () => {
    obj.randomInt += 1;
  };
</script>

{JSON.stringify(obj)}

<button on:click={increment} style="margin:1rem 0">
  The count is {obj.count}
</button>

<button on:click={doSomethingElse} style="margin:1rem 0">
  Something Else
</button>
