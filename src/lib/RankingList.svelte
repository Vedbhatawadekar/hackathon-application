<script lang="ts">
  import RankingItem from "$lib/RankingItem.svelte";
  import { ScrollArea } from "$lib/components/ui/scroll-area/index.js";

  let { searchQuery } = $props();
  
  const data = [
    { companyName: "Microsoft", stockName: "MSFT", score: 100 },
    { companyName: "Google", stockName: "GOGL", score: 50 },
    { companyName: "Apple", stockName: "AAPL", score: 20 },
    { companyName: "NVidia", stockName: "NVIDIA", score: 10 },
  ];

  function stockMatchesSearchQuery(stock) {
    return searchQuery === "" || stock.companyName.toLowerCase().includes(searchQuery.toLowerCase());
  }
</script>

<div class="flex-1 min-h-0">
  <ScrollArea class="rounded-md border h-full">
    {#each data as stock, index}
      {#if stockMatchesSearchQuery(stock)}
	<RankingItem stockName={stock.stockName} ranking={index + 1} score={stock.score}/>
      {/if}
    {/each}
  </ScrollArea>
</div>

