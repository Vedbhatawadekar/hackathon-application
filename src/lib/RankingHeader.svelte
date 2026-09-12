<script lang="ts">
  import * as Item from "$lib/components/ui/item/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import FunnelPlus from "@lucide/svelte/icons/funnel-plus";
  import FilterTray from "$lib/FilterTray.svelte";

  let { searchQuery = $bindable() } = $props();
  
  let filterTrayOpen = $state(false);
</script>

<div class="flex w-full flex-col mb-5">
  <Item.Root variant="outline">
    <Item.Content class="p-3">
      <Item.Title class="text-3xl text-center mb-3">Sustainability Ranking</Item.Title>
      <!-- <Item.Description -->
      <!--   >A simple item with title and description.</Item.Description -->
									  <!-- 					      > -->
									  <Input type="email" placeholder="Search" class="max-w-xs" bind:value={searchQuery} />
    </Item.Content>
    <Item.Actions>
      <Button variant="outline" size="sm" onclick={() => filterTrayOpen = !filterTrayOpen}><FunnelPlus/></Button>
    </Item.Actions>
  </Item.Root>
  {#if filterTrayOpen}
    <FilterTray/>
  {/if}
</div>
