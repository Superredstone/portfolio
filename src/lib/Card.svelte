<script>
	import { link } from "svelte-spa-router";

	export let title;
	export let description;
	export let image;
	export let href;
</script>

<a class="card" {href} use:link>
	<div>
		<h3>{title}</h3>
		<p>{description}</p>
	</div>
	<img src={image} alt="" />
</a>

<style>
	.card {
		display: flex;
		justify-content: center;
		cursor: pointer;
		border-radius: 20px;
		background-color: var(--secondary);
		width: fit-content;
		padding: 10px 0px 10px 20px;
		color: var(--text);
	}

	img {
		width: 300px;
		aspect-ratio: 16 / 9;
		object-fit: contain;
		border-radius: 20px;
	}

	@media (max-width: 800px) {
		.card {
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}

		img {
			width: 200px;
		}
	}
</style>
