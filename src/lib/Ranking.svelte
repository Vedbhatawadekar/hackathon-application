<script lang="ts">
  import RankingList from "$lib/RankingList.svelte";
  import RankingHeader from "$lib/RankingHeader.svelte";
  
  let searchQuery = $state("");
  
  const data = [
    { companyName: "Microsoft", stockName: "MSFT", score: 100 },
    { companyName: "Google", stockName: "GOGL", score: 50 },
    { companyName: "Apple", stockName: "AAPL", score: 20 },
    { companyName: "NVidia", stockName: "NVIDIA", score: 10 },
  ];
</script>

<div class="w-200 m-auto my-10 h-[calc(100vh-2.5rem)] flex flex-col mbe-0">
  <RankingHeader bind:searchQuery/>

  <RankingList searchQuery={searchQuery} data={data} />
</div>
