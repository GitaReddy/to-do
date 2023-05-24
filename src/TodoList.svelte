<script>
    let items = [];
    let newItem = "";
  
    function addItem() {
      if (newItem) {
        items = [...items, newItem];
        newItem = "";
      }
    }
    function deleteItem(index) {
    items = items.filter((_, i) => i !== index);
  }
  </script>
  <main>
   
  <form on:submit|preventDefault={addItem}>
    <label for="name">ToDo List</label><br/>
   
    <input type="text" bind:value={newItem} placeholder="Add an item" />
    <button type="submit">Add</button>
  </form>
  
  </main>
  <ul>
    {#each items as item, index (item.id)}
      <li>
        {item}
        <button on:click={() => deleteItem(index)}>Delete</button>
      </li>
    {/each}
  </ul>
  
  
  
    