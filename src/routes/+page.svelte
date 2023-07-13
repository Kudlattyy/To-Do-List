<script lang="ts">
	import '$lib/styles/app.scss';

	let newTask = '';
	let Task: { Nazwa: string; status: boolean }[] = [];

	const addNewTask = () => {
		if (Task[0] != undefined) {
			Task = [...Task, { Nazwa: newTask, status: false }];
			newTask = '';
		} else {
			Task = [{ Nazwa: newTask, status: false }];
			newTask = '';
		}
	};
</script>

<section>
	<div>
		<h1>To Do List</h1>
	</div>
</section>

<div class="inputText">
	<input bind:value={newTask} type="text" placeholder="Dodaj Nowe Zadania..." />
	<button on:click={addNewTask}> Dodaj</button>
</div>

<div>
	{#each Task as tasks, i}
		<div>
			{tasks.Nazwa}
		</div>
	{/each}
</div>

<style lang="scss">
	h1 {
		font-size: 5rem;
		font-family: 'Anton', sans-serif;
		-webkit-text-stroke: 1px #435fff;
		text-transform: uppercase;
		animation: test 1s;
		margin: 0;
	}

	.Test {
		display: flex;
		justify-content: center;
		justify-content: space-around;
		div {
			padding: 10px;
			border: solid 2px #fff;
			background-color: grey;
		}
	}

	section {
		display: flex;
		justify-content: center;
	}

	@keyframes test {
		from {
			transform: translateY(400px);
		}
		to {
			transform: translateY(0vh);
		}
	}
</style>
