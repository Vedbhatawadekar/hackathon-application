<script lang="ts">
  import * as Item from "$lib/components/ui/item/index.js";
  import { Separator } from "$lib/components/ui/separator/index.js";
  import RankingItemDialog from "$lib/RankingItemDialog.svelte";
  let { stock, ranking } = $props();

</script>

<div class="flex w-full flex-col gap-6">
  <Item.Root variant="outline" class="w-full">
    <div class="text-center p-3">
      <p class="text-3xl">#{ranking}</p>
      
      <Separator />
      Overall score:
      <br/>
      {stock.score}
    </div>
    <Item.Content>
      <Item.Title>{stock.stockName}</Item.Title>
      <Item.Description
	>50%</Item.Description
	      >
    </Item.Content>
    <Item.Actions>
      <RankingItemDialog stock={stock} ranking={ranking}/>
    </Item.Actions>
  </Item.Root>
</div>
