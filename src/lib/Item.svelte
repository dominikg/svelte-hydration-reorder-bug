<script>
  export let item = {};
</script>

<div class="item">
  <!-- wrapping span.name in #if causes the reorder -->
  {#if item.name}
    <span class="name">
      {item.name}
    </span>
  {/if}

  <span>something</span>

</div>

<style>
.name {
  color: white;
  background-color: red;
}
</style>
