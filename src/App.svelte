<script>
	import Nav from "./Nav.svelte";
	import Landing from "./Landing.svelte";
	import About from "./About.svelte";
	import Skills from "./Skills.svelte";
	import Projects from "./Projects.svelte";
	import Contact from "./Contact.svelte";
	let page = "About";

	export function setPage(newPage){
		console.log(newPage)
	}
</script>

<Nav bind:page />
{#if page === "Landing"}
	<Landing/>
{:else if page === "About"}
	<About/>
{:else if page === "Skills"}
	<Skills/>
{:else if page === "Projects"}
	<Projects/>
{:else if page === "Contact"}
	<Contact />
{/if}