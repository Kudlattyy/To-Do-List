<script lang="ts">
	import '$lib/styles/app.scss';
</script>

<section>
	<div class="Main">
		<div class="Left-Panel">Menu</div>
		<div class="Right-Panel">
			<div class="Wall-Tittle">PlaceHolder</div>
			<div class="Wall">
				<div class="Stickers">
					<div>1</div>
					<div>2</div>
					<div>3</div>
					<div>4</div>
					<div>5</div>
					<div>6</div>
				</div>
			</div>
		</div>
	</div>
</section>

<style>
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
</style>
