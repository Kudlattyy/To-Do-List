<script lang="ts">
	import '$lib/styles/app.scss';
	import { scale,fly } from 'svelte/transition';

	let boolean = false;
	function OpenMenuAddNewTask() {
		boolean = true;
	}

	function Sumbit() {
		todoList = [...todoList, { Text: newItem }];
		newItem = '';
		boolean = false;
	}

	let newItem = '';

	let todoList: any = [];
</script>

<section>
	{#if boolean}
		<div class="OffBackground" transition:fly={{ delay: 500, duration: 500}}>
			<div class="Adding">
				<input bind:value={newItem} type="text" placeholder="Name of your task:  " />
				<button class="sumbit" on:click={Sumbit}> Add New </button>
			</div>
		</div>
	{/if}

	<div class="Main">
		<div class="Left-Panel">
			<button class="AddNewTask" on:click={OpenMenuAddNewTask}> Add New Task</button>
		</div>
		<div class="Right-Panel">
			<div class="Wall-Tittle">To Do List</div>
			<div class="Wall">
				<div class="Stickers">
					{#each todoList as item, index}
						<div>{item.Text}</div>
					{/each}
				</div>
			</div>
		</div>
	</div>
</section>

<style lang="scss">
	@import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Merriweather+Sans:wght@300&display=swap');

	section {
		width: 100%;
		height: 100%;
		display: grid;
		place-items: center;
	}

	.Main {
		background-color: #fafafa;
		height: 750px;
		width: 75%;
		box-shadow: 3px 3px 3px 3px rgba(0, 0, 0, 0.3);
		border-radius: 10px;
		display: flex;
		flex-wrap: wrap;
	}

	.Left-Panel {
		height: 725px;
		width: 15%;
		background-color: #f4f4f4;
		margin: 15px;
		border-radius: 10px;
		display: flex;
		justify-content: center;
		.AddNewTask {
			width: 75%;
			height: 40px;
			background-color: #3b93f6;
			border-radius: 10px;
			font-family: 'Merriweather Sans', sans-serif;
		}
	}

	.Right-Panel {
		width: 82%;
		display: flex;
		flex-wrap: wrap;
	}

	.Wall-Tittle {
		height: 100px;
		width: 99%;
		background-color: #f4f4f4;
		margin-top: 18px;
		border-radius: 10px;
		display: flex;
		justify-content: center;
		align-items: center;
		font-family: 'Anton', sans-serif;
		color: #3b93f6;
		font-size: 3rem;
	}

	.Wall {
		height: 600px;
		width: 99%;
		border: #efefef 2px solid;
		border-radius: 10px;
	}

	.Stickers {
		display: grid;
		place-items: center;
		grid-template-columns: 33% 33% 33%;
		grid-template-rows: minmax(350px, auto);
	}

	.OffBackground {
		width: 100vw;
		height: 100vh;
		background-color: rgba(82, 82, 82, 0.318);
		position: absolute;
		z-index: 2;
		display: grid;
		place-items: center;
		.Adding {
			width: 25%;
			height: 700px;
			background-color: #efefef;
			display: flex;
			justify-content: center;
			justify-content: space-around;
			Input {
				width: 75%;
				height: 50px;
				margin-top: 25px;
			}
			.sumbit {
				margin-top: 25px;
				width: 20%;
				height: 50px;
				background-color: green;
				font-family: 'Merriweather Sans', sans-serif;
				color: floralwhite;
				border-radius: 10px;
			}
		}
	}
</style>
