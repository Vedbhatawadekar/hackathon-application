<script lang="ts">
  import * as Dialog from "$lib/components/ui/dialog/index.js";
  import { Button, buttonVariants } from "$lib/components/ui/button/index.js";
  import DialogTable from "$lib/DialogTable.svelte";
  
  let { stock, ranking } = $props();
</script>

<Dialog.Root>
  <form>
    <Dialog.Trigger
      type="button"
      class={buttonVariants({ variant: "outline" })}
      >
      Details
    </Dialog.Trigger>
    <Dialog.Content class="sm:max-w-[600px] h-200 p-10">
      <Dialog.Header>
	<Dialog.Title class="text-5xl">{stock.stockName}</Dialog.Title>
	<Dialog.Description class="text-xl">
	  Overall score: #{ranking}
	</Dialog.Description>
      </Dialog.Header>
      <DialogTable stock={stock}/>
      <Dialog.Footer>
	<!-- <Dialog.Close -->
	<!--   type="button" -->
	<!--   class={buttonVariants({ variant: "outline" })} -->
	<!--   > -->
	<!--   Close -->
	<!-- </Dialog.Close> -->


      </Dialog.Footer>
    </Dialog.Content>
  </form>
</Dialog.Root>
