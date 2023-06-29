<script lang="ts">
	import Router, { location, link } from "svelte-spa-router";
	import Home from "./Home.svelte";
	import Navbar from "./lib/Navbar.svelte";
	import Footer from "./lib/Footer.svelte";
	import Contact from "./Contact.svelte";
	import Projects from "./Projects.svelte";

	let current_page = "/";
	location.subscribe((data) => {
		current_page = data;
	});

	let routes = {
		"/": Home,
		"/home": Home,
		"/projects": Projects,
		"/contact": Contact,
	};
</script>

<svelte:head>
	<title>Patrick Canal</title>
</svelte:head>
<Navbar {current_page} />
<Router {routes} />
<Footer />
