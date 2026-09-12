<script lang="ts">
  import RankingItem from "$lib/RankingItem.svelte";
  import { ScrollArea } from "$lib/components/ui/scroll-area/index.js";

  let { searchQuery, data } = $props();
  
  function stockMatchesSearchQuery(stock) {
    return searchQuery === "" || stock.companyName.toLowerCase().includes(searchQuery.toLowerCase());
  }
</script>

<div class="flex-1 min-h-0">
  <ScrollArea class="rounded-md border h-full">
    {#each data as stock, index}
      {#if stockMatchesSearchQuery(stock)}
	<RankingItem stock={stock} ranking={index + 1} />
      {/if}
    {/each}
  </ScrollArea>
</div>

