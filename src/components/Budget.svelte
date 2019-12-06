<script>
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	export let id;
	export let description;
	export let amount;

	function onDeleteClicked() {
		dispatch('delete', {
			'id': id
		});
	}
</script>

<div>
	<p>{description} : IDR {amount} - <button on:click={onDeleteClicked}>Delete</button></p>
</div>