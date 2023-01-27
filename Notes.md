### Links
* https://svelte.dev/docs
* https://svelte.dev/examples/hello-world

### Important notes

* You can have only 1 top-level `<style></style>` tag per svelte file/component
* Style tags properties only apply at the svelte filte/component
* You can have only 1 instance-level `<script></script>` element per svelte file/component


### Global CSS Selector

* :global(h1){...properties}
* :global(.hello){...properties}
* @keyframes -global-zoom{...properties}

### Reactive declarations
```typescript
const count = 1;
$: double = count * 2;
```

### Some elements tags can be passed directly as variables (short-hand attributes)
```typescript
<script lang="ts">
const src="assets/photo.png";
</script>

<img alt="logo" {src} />
```

### Spreading props (Just Like React Does)
```typescript
<script lang="ts">
	import PackageInfo from './PackageInfo.svelte';

	const pkg = {
		name: 'svelte',
		version: 3,
		speed: 'blazing',
		website: 'https://svelte.dev'
	};
</script>

<PackageInfo {...pkg} />
```

```typescript
<script>
	export let name;
	export let version;
	export let speed;
	export let website;

	$: href = `https://www.npmjs.com/package/${name}`;
</script>

<p>
	The <code>{name}</code> package is {speed} fast. Download version {version}
	from
	<a {href}>npm</a>
	and <a href={website}>learn more here</a>
</p>

<style>
	code {
		font-family: Menlo;
		padding: 0.1em 0.2em;
		border-radius: 0.2em;
	}
</style>
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

### Components events nesting
Unlike DOM events, component events don't bubble. If you want to listen to an event on some deeply nested component, the intermediate components must forward the event.

In this case, we have the same App.svelte and Inner.svelte as in the previous chapter, but there's now an Outer.svelte component that contains `<Inner/>`

But that's a lot of code to write, so Svelte gives us an equivalent shorthand — an on:message event directive without a value means 'forward all message events'.

```typescript
<script>
	import Inner from './Inner.svelte';
</script>

<Inner on:message />
```