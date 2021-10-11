<script>
  import { flip } from "svelte/animate";
  import { dndzone } from "svelte-dnd-action";
  export let items;
  const flipDurationMs = 300;
  const dropTargetStyle = 	{outline: 'rgba(0, 0, 0, 0) solid 0px'}

  function handleDndConsider(e) {
    items = e.detail.items;
  }

  function handleDndFinalize(e) {
    items = e.detail.items;
  }
</script>

<section  use:dndzone={{ items, flipDurationMs, dropTargetStyle }}  on:consider={handleDndConsider}  on:finalize={handleDndFinalize}>
  {#each items as item (item.id)}
    <div style={'background-color:' + item.color } animate:flip={{ duration: flipDurationMs }}>
      {item.name}
    </div>
  {/each}
</section>

<style>
  section {
    width: 80px;
    height: 270px;
    margin-left: 80px;
    align-content: center;
  }

  div {    
    color: white;
    width: 60px;
    height: 60px;
    margin: 10px;
    text-align: center;
    justify-content: center;
    cursor: move;
  }
</style>
