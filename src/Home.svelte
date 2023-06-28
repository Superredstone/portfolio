<script lang="ts">
	import {
		IconBrandJavascript,
		IconBrandRust,
		IconBrandGolang,
		IconBrandPython,
		IconBrandHtml5,
		IconBrandCss3,
		IconBrandReact,
		IconBrandSvelte,
		IconBrandVue,
	} from "@tabler/icons-svelte";
</script>

<main>
	<h1 class="title">$ whoami</h1>
	<p>
		I'm an Italian <span class="emoji">🇮🇹</span> boy who has loved programming
		since he was 12, <br /> I love experimenting with new technologies.<span
			class="emoji">🤖</span
		>
	</p>
	<div class="lists">
		<div class="list1">
			<h2>Programming languages:</h2>
			<ul>
				<li>Javascript <IconBrandJavascript /></li>
				<li>Rust <IconBrandRust /></li>
				<li>Golang <IconBrandGolang /></li>
				<li>Python <IconBrandPython /></li>
				<li>HTML <IconBrandHtml5 /></li>
				<li>CSS <IconBrandCss3 /></li>
			</ul>
		</div>
		<div class="list2">
			<h2>Javascript frameworks I know:</h2>
			<ul>
				<li>React <IconBrandReact /></li>
				<li>
					Svelte <IconBrandSvelte class="icon" />
				</li>
				<li>Vue <IconBrandVue /></li>
			</ul>
		</div>
	</div>
</main>

<style>
	main {
		font-size: 1.8rem;
	}

	.emoji {
		padding: 0 6px 0 6px;
	}

	.lists {
		display: grid;
		grid-template-columns: 50% 50%;
	}

	@media (max-width: 1500px) {
		.lists {
			grid-template-rows: 100%;
			grid-template-columns: 100%;
		}
	}

	.title {
		white-space: nowrap;
	}

	.title::after {
		margin-left: 7px;
		content: "";
		width: 20px;
		height: 2.7rem;
		background-color: var(--text);
		display: inline-block;
		animation: cursor-blink 1.5s steps(2) infinite;
	}

	li {
		font-size: larger;
	}

	@media (max-width: 800px) {
		main {
			font-size: large;
		}

		.title::after {
			height: 2rem;
			width: 15px;
		}
	}

	@keyframes cursor-blink {
		0% {
			opacity: 0%;
		}
	}
</style>
