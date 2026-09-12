<script lang="ts">
  import RankingList from "$lib/RankingList.svelte";
  import * as Item from "$lib/components/ui/item/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
</script>


<div class="flex w-full flex-col">
  <Item.Root variant="outline">
    <Item.Content>
      <Item.Title>Filter</Item.Title>
      <Item.Description
	>A simple item with title and description.</Item.Description>
    </Item.Content>
  </Item.Root>
</div>
