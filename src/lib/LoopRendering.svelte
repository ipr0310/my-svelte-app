<script lang="ts">
  const cats = [
    {
      id: "J---aiyznGQ",
      name: "Keyboard Cat",
    },
    {
      id: "z_AbfPXTKms",
      name: "Maru",
    },
    {
      id: "OUtn3pvWmpg",
      name: "Henri The Existential Cat",
    },
  ];
</script>

<h1>Loop Rendering</h1>

<ul>
  <!-- {#each cats as cat, i} -->
  <!-- If you prefer, you can use destructuring — each cats as { id, name } — and replace cat.id and cat.name with id and name. -->
  {#each cats as { id, name }, index (id)}
    <li>
      <a
        rel="noreferrer"
        target="_blank"
        href="https://www.youtube.com/watch?v={id}"
      >
        {index + 1}: {name}
      </a>
    </li>
  {/each}
</ul>
