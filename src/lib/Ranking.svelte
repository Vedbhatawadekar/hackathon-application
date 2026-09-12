<script lang="ts">
  import RankingItem from "$lib/RankingItem.svelte";
</script>

<ol>
  <RankingItem stockName="MSFT"/>
  <RankingItem stockName="GOGL"/>
  <RankingItem stockName="AAPL"/>
</ol>


<style>
  ol {
    size: 0 auto;
    margin: 100px;
    background-color: red;
  }
</style>
