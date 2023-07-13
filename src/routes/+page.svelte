<script lang="ts">
	import '$lib/styles/app.scss';
</script>

<section>
	<div>
		<h1>To Do List</h1>
	</div>
</section>

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
