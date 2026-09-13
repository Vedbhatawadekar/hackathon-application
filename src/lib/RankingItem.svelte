<script lang="ts">
  import * as Item from "$lib/components/ui/item/index.js";
  import { Separator } from "$lib/components/ui/separator/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import RankingItemDialog from "$lib/RankingItemDialog.svelte";
  let { stock, ranking, setHover, addToComparison, removeFromComparison, comparisonList } = $props();

  function isBeingCompared() {
    for (const s of comparisonList) {
      if (s.companyName == stock.companyName) {
	return true;
      }
    }

    return false;
  }
</script>


<div class="flex w-full flex-col gap-6" onmouseenter={() => setHover(stock)} onmouseleave={() => setHover(null)}>
  <Item.Root variant="outline" class="w-full">
    <div class="text-center p-3">
      <p class="text-3xl">#{ranking}</p>
      
      <Separator />
      Overall score:
      <br/>
      {stock.score}
    </div>
    <Item.Content>
      <Item.Title class="text-1xl">{stock.stockName}</Item.Title>
      <Item.Description
	>50%</Item.Description
	      >
    </Item.Content>
    <Item.Actions>
      <Button onclick={() => {
	if (isBeingCompared()) {
	removeFromComparison(stock);
	} else {
	addToComparison(stock);
	}
	}}>{isBeingCompared() ? "Remove" : "Compare"}</Button>
      <RankingItemDialog stock={stock} ranking={ranking}/>
    </Item.Actions>
  </Item.Root>
</div>

