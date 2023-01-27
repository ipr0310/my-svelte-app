<script lang="ts">
  // We can easily specify default values for props in Nested.svelte:
  export let answer = 50;
  export let name = "Naruto";
</script>

<h1>Component Props</h1>

<p>
  The name is {name}
</p>

<p>
  The answer is {answer}
</p>
