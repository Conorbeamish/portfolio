<script>
	import Nav from "./Nav.svelte";
	import Landing from "./Landing.svelte";
	import About from "./About.svelte";
	import Skills from "./Skills.svelte";
	import Projects from "./Projects.svelte";
	import Contact from "./Contact.svelte";
	import Footer from "./Footer.svelte";
	let page = "Landing";

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
<Footer/>