<script lang="ts">
  let coordinates = { x: 0, y: 0 };

  const handleMouseMove = (event: MouseEvent) => {
    coordinates.x = event.clientX;
    coordinates.y = event.clientY;
  };

  $: ({ x, y } = coordinates);
</script>

<h1>DOM Events</h1>

<div on:mousemove={handleMouseMove}>
  The mouse position is {x} x {y}
</div>

<style>
  div {
    width: 100%;
    height: 200px;
    background: rgba(0, 0, 0, 0.05);
  }
</style>
