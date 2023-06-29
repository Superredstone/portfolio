<script lang="ts">
	import { link } from "svelte-spa-router";

	export let current_page: string;

	function navitemsClass(): string {
		return "current-page nav-item";
	}
</script>

<nav>
	<h1>
		<a href="#/" use:link class="home-button">Patrick Canal</a>
	</h1>
	<div class="nav-items">
		<input type="checkbox" id="navbar-toggle" />
		<label for="navbar-toggle" class="hamburger">&#9776;</label>

		<div class="menu">
			<a
				href="/"
				use:link
				class={current_page === "/" ? navitemsClass() : "nav-item"}>About me</a
			>
			<a
				href="/projects"
				use:link
				class={current_page === "/projects" ? navitemsClass() : "nav-item"}
				>Projects</a
			>
			<a
				href="/contact"
				use:link
				class={current_page === "/contact" ? navitemsClass() : "nav-item"}
				>Contact</a
			>
		</div>
	</div>
</nav>

<style>
	nav {
		width: auto;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	h1 {
		font-size: 1.8rem;
	}

	input[type="checkbox"] {
		display: none;
	}

	.hamburger {
		display: none;
		font-size: 24px;
		user-select: none;
	}

	.menu > a {
		padding-left: 20px;
	}

	@media (max-width: 800px) {
		.menu {
			display: none;
			position: absolute;
			background-color: var(--secondary);
			right: 0;
			left: 0;
			margin-top: 20px;
			text-align: center;
			padding: 16px 0;
			opacity: 0%;
			z-index: 100;
			transition: all 0.25s;
		}

		input[type="checkbox"]:checked ~ .menu {
			display: flex;
			flex-direction: column;
			opacity: 100%;
			gap: 50px;
		}

		.hamburger {
			display: block;
		}
	}

	a {
		text-decoration: none;
		color: var(--text);
		transition: color 0.25s;
	}

	a:hover {
		color: var(--primary);
	}

	.current-page {
		color: var(--primary);
	}

	.home-button {
		position: relative;
		background-image: linear-gradient(120deg, var(--primary), var(--accent));
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	.home-button::after {
		content: "";
		position: absolute;
		width: 100%;
		transform: scaleX(0);
		height: 2px;
		bottom: 0;
		left: 0;
		background-image: linear-gradient(120deg, var(--primary), var(--accent));
		transform-origin: bottom right;
		transition: transform 0.25s ease-out;
	}

	.home-button:hover::after {
		transform: scaleX(1);
		transform-origin: bottom left;
	}
</style>
