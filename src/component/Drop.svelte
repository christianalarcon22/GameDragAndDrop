<script>
  import { flip } from "svelte/animate";
  import { dndzone } from "svelte-dnd-action";
  export let items;  
  const flipDurationMs = 300;

  function handleDndConsider(e) {
    items = e.detail.items;
  }
  
  function handleDndFinalize(e) {
    items = e.detail.items;   
  }
</script>

<section use:dndzone={{ items, flipDurationMs}} on:consider={handleDndConsider} on:finalize={handleDndFinalize}>
  {#each items as item (item.id)}
    <div style={'background-color:' + item.color} animate:flip={{ duration: flipDurationMs }}>
      {item.name}
    </div>
  {/each}
</section>

<style>
  section {
    color: white;
    background-color:darkgrey;    
    width: 60px;
    height: 60px;
    margin-left: 45px;   
  
  }  
</style>

