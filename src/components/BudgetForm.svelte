<script>
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	let description = '';
	let amount = '';

	function clear() {
		description = '';
		amount = '';
	}

	function onAddBudgetClicked(e) {
		dispatch('add', {
			description: description,
			amount: amount
		});
		clear();
	}
</script>

<form>
	<input type="text" placeholder="Budget description" bind:value={description}/>
	<input type="number" placeholder="Amount" bind:value={amount}>
	<button on:click|preventDefault={onAddBudgetClicked}>+ Add</button>
</form>