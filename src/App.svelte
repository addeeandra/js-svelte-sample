<script>
	import BudgetList from './components/BudgetList.svelte';
	import BudgetForm from './components/BudgetForm.svelte';

	let budgetList = [];

	function onBudgetAdded(event) {
		console.log('ADDING', event.detail);
		budgetList = [...budgetList, event.detail];
	}
	
	function onBudgetDeleted(event) {
		console.log('DELETING', event.detail);
		budgetList = [...budgetList.filter((item, index) => index != event.detail.id)];
	}
</script>

<h1>Budget Planner</h1>
<BudgetForm on:add={onBudgetAdded}/>
<BudgetList on:delete={onBudgetDeleted} budgets={budgetList}/>