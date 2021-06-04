<script>
  import Block from "./Block.svelte";

  let current = "";
</script>

<div class="wrapper">
  <div
    class="parent {current === 'red' ? 'active' : ''}"
    on:click={() => (current = current === 'red' ? '' : 'red')}
  >
    <Block class="red" />
  </div>
  <div
    class="parent {current === 'green' ? 'active' : ''}"
    on:click={() => (current = current === 'green' ? '' : 'green')}
  >
    <Block class="green" />
  </div>
  <div
    class="parent {current === 'blue' ? 'active' : ''}"
    on:click={() => (current = current === 'blue' ? '' : 'blue')}
  >
    <Block class="blue" />
  </div>
</div>

<style>
  .wrapper {
    display: flex;
  }
  .parent :global(.red) {
    background-color: red;
    opacity: 1;
  }
  .parent :global(.green) {
    background-color: green;
    opacity: 1;
  }
  .parent :global(.blue) {
    background-color: blue;
    opacity: 1;
  }
  .active {
    opacity: 0;
  }
</style>
