<script lang="ts">
  import Ranking from '$lib/Ranking.svelte';
  import Description from "$lib/Description.svelte";
  import DataPanel from "$lib/DataPanel.svelte";
  
  interface Company {
    companyName: string,
    stockName: string,
    score: number,
  };
  
  const data: Array<Company> = [
    { companyName: "Microsoft", stockName: "MSFT", score: 100 },
    { companyName: "Google", stockName: "GOGL", score: 50 },
    { companyName: "Apple", stockName: "AAPL", score: 20 },
    { companyName: "NVidia", stockName: "NVIDIA", score: 10 },
  ];

  let hover = $state(null);
  let comparisonList = $state([]);

  function addToComparison(company: Company) {
    comparisonList = comparisonList.concat([company]);
  }

  function removeFromComparison(company: Company) {
    comparisonList = comparisonList.filter((c) => c !== company);
  }

  function setHover(company: Company) {
    hover = company;
  }
</script>

<div class="mbe-0 h-[calc(100vh-2.5rem)] mbs-10 justify-center flex flex-row gap-10">
  <DataPanel comparisonList={comparisonList} hover={hover}/>
  <Ranking data={data} setHover={setHover} addToComparison={addToComparison} removeFromComparison={removeFromComparison} comparisonList={comparisonList}/>
  <Description/>
</div>

