<script>
	import Router from 'svelte-spa-router'
	import Nav from "./Nav.svelte";
	import Landing from "./Landing.svelte";
	import About from "./About.svelte";
	import Skills from "./Skills.svelte";
	import Projects from "./Projects.svelte";
	import Contact from "./Contact.svelte";
	import Footer from "./Footer.svelte";

	const routes = {
		"/": Landing,
		"/about": About,
		"/skills": Skills,
		"/projects": Projects,
		"/contact": Contact
	}
</script>

<Nav />
<Router {routes}/>

<!-- <Footer/> -->