<script>
	import Form from "./form.svelte";
	import Counter from "./counter.svelte";
	import TodoList from './todo-list.svelte';

	export let name;

</script>

<main>
	<h1>Props: {name}!</h1>


	<Counter counter={2} />

	<Form/>

	<TodoList/>
</main>


<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>