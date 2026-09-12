<script lang="ts">
  import RankingItem from "$lib/RankingItem.svelte";
  import { ScrollArea } from "$lib/components/ui/scroll-area/index.js";

  const data = [
    { stockName: "MSFT", score: 100 },
    { stockName: "GOGL", score: 50 },
    { stockName: "AAPL", score: 20 },
  ]
</script>

<ScrollArea class="rounded-md border w-200 h-dvh m-auto my-10">
  {#each data as stock, index}
    <RankingItem stockName={stock.stockName} ranking={index + 1} score={stock.score}/>
  {/each}
</ScrollArea>

