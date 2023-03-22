<script lang="ts">
  const count = 4;

  let active = true;

  const toggle = () => {
    active = !active;
  };
</script>

<h1>Conditional Rendering</h1>

<button on:click={toggle}>Toggle</button>

{#if active}
  <span style="color:green">The component is really activated</span>
{/if}

{#if !active}
  <span style="color:red">The component is NOT activated</span>
{/if}

<!-- Since the two conditions — if user.loggedIn and if !active — are mutually exclusive, we can simplify this component slightly by using an else block: -->
{#if active}
  <h4>Click the button in order to disable it</h4>
{:else}
  <h4>Click the button to activate it</h4>
{/if}

<!-- Multiple conditions can be 'chained' together with else if: -->
{#if count > 10}
  <span>Count is greater than 10</span>
{:else if count > 5}
  <span>Count is greater than 5</span>
{:else if count < 5}
  <span>Count is lower than 5</span>
{:else}
  <span>Count is between 5 and 10</span>
{/if}
