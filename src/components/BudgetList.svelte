<script>
	import Budget from './Budget.svelte';

	export let budgets;
</script>

<h2>Recorded Budgets</h2>
<ul>
	{#each budgets as budget, i}
	<li>
		<Budget 
			id={i}
			description={budget.description}
			amount={budget.amount}
			on:delete />
	</li>
	{/each}
</ul>

<p>
	Subtotal : {budgets.map((item) => item.amount).reduce((a, b) => a + b, 0)}
</p>