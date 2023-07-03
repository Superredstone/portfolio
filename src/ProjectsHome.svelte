<script>
	import Card from "../src/lib/Card.svelte";
</script>

<main>
	<Card
		title="Endless runner"
		description="A simple endless runner that I wrote using PhaserJS."
		image="endless_runner.png"
		href="/projects/endless-runner"
	/>
</main>

<style>
	h1 {
		margin-bottom: 700px;
	}

	main {
		display: grid;
		grid-template-row: auto auto;
		grid-template-column: 1fr;
		grid-gap: 20px;
		margin-bottom: 550px;
	}
</style>
