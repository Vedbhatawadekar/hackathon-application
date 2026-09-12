<script lang="ts">
  import RankingList from "$lib/RankingList.svelte";
  import * as Item from "$lib/components/ui/item/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import FunnelPlus from "@lucide/svelte/icons/funnel-plus";
  import FilterTray from "$lib/FilterTray.svelte";

  let searchQuery = $state("");
  let filterTrayOpen = $state(false);
</script>

<!-- <div class="w-200 m-auto mt-10 h-[calc(100vh-2.5rem)] bg-red-100"> -->
<!--   <div class="flex w-full flex-col"> -->
<!--     <Item.Root variant="outline"> -->
<!--       <Item.Content> -->
<!-- 	<Item.Title>Sustainability Ranking</Item.Title> -->
<!-- 	<Item.Description -->
<!-- 	  >A simple item with title and description.</Item.Description -->
<!-- 						      > -->
<!--       </Item.Content> -->
<!--       <Item.Actions> -->
<!-- 	<Button variant="outline" size="sm">Action</Button> -->
<!--       </Item.Actions> -->
<!--     </Item.Root> -->
<!--   </div> -->

<!--   <RankingList/> -->
<!-- </div> -->


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

  <RankingList searchQuery={searchQuery}/>
</div>
