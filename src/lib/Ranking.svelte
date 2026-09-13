<script lang="ts">
  import RankingList from "$lib/RankingList.svelte";
  import RankingHeader from "$lib/RankingHeader.svelte";
  
  let { data, setHover, addToComparison, removeFromComparison, comparisonList } = $props();
  let searchQuery = $state("");
</script>

<div class="w-200 h-full flex flex-col my-0">
  <RankingHeader bind:searchQuery/>

  <RankingList {searchQuery} {data} {setHover} {addToComparison} {removeFromComparison} {comparisonList}/>
</div>
