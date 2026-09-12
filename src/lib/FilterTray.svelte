<script lang="ts">
  import RankingList from "$lib/RankingList.svelte";
  import * as Item from "$lib/components/ui/item/index.js";
  import Filter from "$lib/Filter.svelte"
  import { Button } from "$lib/components/ui/button/index.js";

  import * as Select from "$lib/components/ui/select/index.js";

  let sortByValue = $state("Overall Score");
  let sectorValue = $state("All");
  let subIndustryValue = $state("All");
  
</script>

<div class="flex w-full flex-col">
  <Item.Root variant="outline">
    <Item.Content class="p-3">
      <div class="grid grid-flow-row grid-cols-3 gap-3">
	<Filter label="Sort by" filterOptions={["Overall Score", "Revenue", "CO2"]} bind:value={sortByValue}/>
	<Filter label="GICS Sector" filterOptions={["All", "Tech", "Automobile", "Excavation"]} bind:value={sectorValue}/>
	<Filter label="GICS Sub-industry" filterOptions={["All", "Tech", "Automobile", "Excavation"]} bind:value={subIndustryValue}/>
      </div>
    </Item.Content>
  </Item.Root>
</div>
