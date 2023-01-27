<script lang="ts">
  let name = "Paul";

  const changeName = () => {
    name = name === "Paul" ? "Paola" : "Paul";
  };

  const string = `this string contains some <strong>HTML!!!</strong>`;
</script>

<h1>Another Component</h1>

<p>Hello World, My Name is {name.toUpperCase()}</p>

<button on:click={changeName}>Change Name</button>

<a
  target="_blank"
  href="https://twitter.com/ipr0310"
  rel="noreferrer"
  style="margin-bottom:2rem"
>
  Link to my Twitter
</a>

<a target="_blank" href="https://github.com/ipr0310" rel="noreferrer">
  Link to my Github Profile
</a>

<p>{@html string}</p>

<!-- 
<style>
  p {
    animation: zoom 2s infinite;
  }
</style> -->
