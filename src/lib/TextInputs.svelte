<script lang="ts">
  // Text area-related import
  import { marked } from "marked";

  let name = "Naruto";

  let a = 1;
  let b = 2;

  let active = false;

  // Group inputs
  let scoops = 1;
  let flavours = ["Mint choc chip"];
  let menu = ["Cookies and cream", "Mint choc chip", "Raspberry ripple"];

  const join = (flavours: string[]) => {
    if (flavours.length === 1) return flavours[0];

    return `${flavours.slice(0, -1).join(", ")} and ${
      flavours[flavours.length - 1]
    }`;
  };

  // Text area
  let textAreaValue = `Some words are *italic*, some are **bold**`;

  // Select inputs
  let questions = [
    {
      id: 1,
      text: `Where did you go to school?`,
    },
    {
      id: 2,
      text: `What is your mother's name?`,
    },
    {
      id: 3,
      text: `What is another personal fact that an attacker could easily find with Google?`,
    },
  ];

  let selected = 0;

  let answer = "";
</script>

<h1>Text Inputs</h1>

<label>
  <input bind:value={name} style="margin-bottom:1em" />
  <span>Hello {name}</span>
</label>

<label>
  A
  <input type="number" bind:value={a} min="0" max="10" />
  <input type="range" bind:value={a} min="0" max="10" />
</label>

<label style="margin:1em 0">
  B
  <input type="number" bind:value={b} min="0" max="10" />
  <input type="range" bind:value={b} min="0" max="10" />
</label>

<p>{a} + {b} = {a + b}</p>

<h2>Checkbox</h2>

<label>
  <input type="checkbox" bind:checked={active} />
  Yes! Send me regular email spam
</label>

{#if active}
  <p>Thank you. We will bombard your inbox and sell your personal details.</p>
{:else}
  <p>You must opt in to continue. If you're not paying, you're the product</p>
{/if}

<button disabled={!active}> Subscribe </button>

<h2>Size</h2>

<label>
  <input type="radio" bind:group={scoops} name="scoops" value={1} />
  One scoop
</label>

<label>
  <input type="radio" bind:group={scoops} name="scoops" value={2} />
  Two scoops
</label>

<label>
  <input type="radio" bind:group={scoops} name="scoops" value={3} />
  Three scoops
</label>

<h2>Flavours</h2>

{#each menu as flavour}
  <label>
    <input
      type="checkbox"
      bind:group={flavours}
      name="flavours"
      value={flavour}
    />
    {flavour}
  </label>
{/each}

{#if !flavours.length}
  <p>Please select at least one flavour</p>
{:else if flavours.length > scoops}
  <p>Can't order more flavours than scoops!</p>
{:else}
  <p>
    You ordered {scoops}
    {scoops === 1 ? "scoop" : "scoops"}
    of {join(flavours)}
  </p>
{/if}

<h2>Textarea Inputs</h2>

{@html marked(textAreaValue)}

<textarea
  bind:value={textAreaValue}
  style="width:100%;height:100px;margin-bottom:2em;"
/>

<h2>Select Inputs</h2>

<select bind:value={selected} on:change={() => (answer = "")}>
  <option value={0} aria-readonly="true" disabled>Pick a question</option>

  {#each questions as question}
    <option value={question.id}>
      {question.text}
    </option>
  {/each}
</select>

{#if selected}
  <p>
    You had selected question #{selected}
  </p>
{:else}
  <p>You have picked no questions</p>
{/if}
