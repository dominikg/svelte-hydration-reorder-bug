<script>
  import { sortItems } from "./lib/sortItems";
  import Item from "./lib/Item.svelte";

  let sortByName = true;
  let items = [
    { id: 1, name: "item 1", value: 3 },
    { id: 2, name: "item 2", value: 2 },
    { id: 3, name: "item 3", value: 1 },
  ];

  $: sortedItems = sortItems(items, sortByName);

  const handleChangeSort = () => {
    sortByName = !sortByName;
  };
</script>

<div>
  <button on:click={handleChangeSort}> change sort </button>

  <div>
    sort by name: {sortByName}
  </div>

  {#each sortedItems as item (item.id)}
      <Item {item} />
  {/each}
</div>
