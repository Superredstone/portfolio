<script>
	import { link } from "svelte-spa-router";
</script>

<nav>
	<h1>
		<a href="#/" use:link class="home-button">Patrick Canal</a>
	</h1>
	<div class="nav-items">
		<a href="/" use:link>About me</a>
		<a href="/contact" use:link>Contact</a>
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

	a {
		text-decoration: none;
		color: var(--text);
		transition: color 0.25s;
	}

	a:hover {
		color: var(--primary);
		transform: translateY(10px);
	}

	.nav-items > a {
		margin-left: 30px;
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
