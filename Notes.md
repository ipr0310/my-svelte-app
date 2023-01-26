### Important notes

* You can have only 1 top-level `<style></style>` tag per svelte file/component
* Style tags properties only apply at the svelte filte/component
* You can have only 1 instance-level `<script></script>` element per svelte file/component


### Global CSS Selector

* :global(h1){...properties}
* :global(.hello){...properties}
* @keyframes -global-zoom{...properties}
  

### Some elements tags can be passed directly as variables (short-hand)
```typescript
<script lang="ts">
const src="assets/photo.png"
</script>

<img alt="logo" {src} />
```
