<script lang="ts">
	import Router, { location, link } from "svelte-spa-router";
	import Home from "./Home.svelte";
	import Navbar from "./lib/Navbar.svelte";
	import Footer from "./lib/Footer.svelte";
	import Contact from "./Contact.svelte";

	let routes = {
		"/": Home,
		"/home": Home,
		"/contact": Contact,
	};
</script>

<svelte:head>
	<title>Patrick Canal</title>
</svelte:head>
<Navbar />
<Router {routes} />
<Footer />
