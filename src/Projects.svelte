<script>
  import Router from "svelte-spa-router";
	import { wrap } from "svelte-spa-router/wrap";

	import ProjectsHome from "./ProjectsHome.svelte";

	const prefix = "/projects";
	const routes = {
		"/": ProjectsHome, 
		"/endless-runner": wrap({
			asyncComponent: () => import ("./EndlessRunner.svelte")
		})
	};
</script>

<Router {routes} {prefix} /> 
