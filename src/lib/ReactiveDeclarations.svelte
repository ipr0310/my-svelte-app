<script lang="ts">
  let count = 1;
  const firstName = "Paul";
  const lastName = "Lopez";

  // This variable needs to be explictly updated
  // let double = count * 2;

  // This variable will always get updated when the variable count receive changes
  $: double = count * 2;

  // Reactive statement
  // This will log only when the variable count gets updates
  $: console.log("Count:", count);

  // This variable will always get updated when the variable firstName or lastName receive changes
  //   $: fullname = firstName + " " + lastName;

  // More examples
  //   $: sum = a + b + c; || launch when A or B or C receive changes
  //   $: result = calculate(num1, num2); || launch when calculate or num1 or num2 recive changes
  //   $: doSomething(a, b); || launch when doSomething or A or B recive changes

  const increment = () => {
    count++;
  };

  const decrement = () => {
    count--;
  };

  const multiply = () => {
    count = count * count;
  };

  const doSomething = () => {
    console.log(double);
  };
</script>

<h1>Reactive declarations & statements</h1>

<div style="display:flex">
  <button on:click={decrement}> - </button>

  <p style="margin:1em">
    {count} * 2 = {double}
  </p>

  <button on:click={increment}> + </button>

  <button on:click={multiply}> Multiply </button>

  <button on:click={doSomething}> Something Else </button>
</div>
