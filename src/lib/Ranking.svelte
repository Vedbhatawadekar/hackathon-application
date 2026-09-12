<script lang="ts">
  import RankingList from "$lib/RankingList.svelte";
  import * as Item from "$lib/components/ui/item/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import FunnelPlus from "@lucide/svelte/icons/funnel-plus";
  import FilterTray from "$lib/FilterTray.svelte";

  let searchQuery = $state("");
  let filterTrayOpen = $state(false);
  
  const data = [
    { companyName: "Microsoft", stockName: "MSFT", score: 100 },
    { companyName: "Google", stockName: "GOGL", score: 50 },
    { companyName: "Apple", stockName: "AAPL", score: 20 },
    { companyName: "NVidia", stockName: "NVIDIA", score: 10 },
  ];
</script>

<div class="w-200 m-auto my-10 h-[calc(100vh-2.5rem)] flex flex-col">
  <div class="flex w-full flex-col">
    <Item.Root variant="outline">
      <Item.Content>
	<Item.Title>Sustainability Ranking</Item.Title>
	<Item.Description
	  >A simple item with title and description.</Item.Description
						      >
	<Input type="email" placeholder="Company Name" class="max-w-xs" bind:value={searchQuery} />
      </Item.Content>
      <Item.Actions>
	<Button variant="outline" size="sm" onclick={() => filterTrayOpen = !filterTrayOpen}><FunnelPlus/></Button>
      </Item.Actions>
    </Item.Root>
  </div>
  {#if filterTrayOpen}
    <FilterTray/>
  {/if}

  <RankingList searchQuery={searchQuery} data={data} />
</div>
