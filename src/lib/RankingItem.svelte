<script lang="ts">
  import * as Item from "$lib/components/ui/item/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import { Separator } from "$lib/components/ui/separator/index.js";

  let { stockName, ranking, score } = $props();
</script>

<div class="flex w-full flex-col gap-6">
  <Item.Root variant="outline" class="w-full">
    <div class="text-center">
      <p class="text-3xl">#{ranking}</p>
      
      <Separator />
      Overall score:
      <br/>
      {score}
    </div>
    <Item.Content>
      <Item.Title>{stockName}</Item.Title>
      <Item.Description
	>50%</Item.Description
	      >
    </Item.Content>
    <Item.Actions>
      <Button variant="outline" size="sm">Details</Button>
    </Item.Actions>
  </Item.Root>
</div>
