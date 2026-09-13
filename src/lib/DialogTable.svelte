<script lang="ts">
  let { stock } = $props();

  import TableEntry from "$lib/TableEntry.svelte";
</script>

<table class="text-center border-separate border-spacing-5 border-gray-400 dark:border-gray-500">
  <tbody>
    <tr>
      <TableEntry data={15} heading="CO2"/>
      <TableEntry data={15} heading="CO2"/>
      <TableEntry data={15} heading="CO2"/>
      <TableEntry data={15} heading="CO2"/>
    </tr>
    <tr>
      <TableEntry data={15} heading="CO2"/>
      <TableEntry data={15} heading="CO2"/>
      <TableEntry data={15} heading="CO2"/>
      <TableEntry data={15} heading="CO2"/>
    </tr>
  </tbody>
</table>
