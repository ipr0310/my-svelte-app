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

### Event modifiers

* `preventDefault` — calls event.preventDefault() before running the handler
* `stopPropagation` — calls event.stopPropagation(), preventing the event reaching the next element
* `passive` — improves scrolling performance on touch/wheel events (Svelte will add it automatically where it's safe to do so)
* `nonpassive` — explicitly set passive: false
* `capture` — fires the handler during the capture phase instead of the bubbling phase
* `once` — remove the handler after the first time it runs
* `self` — only trigger handler if event.target is the element itself
* `trusted` — only trigger handler if event.isTrusted is true. I.e. if the event is triggered by a user action.
  
Modifiers can be chained together, e.g. on:click|once|capture={...}.