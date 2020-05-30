<script>
    import {link} from 'svelte-spa-router'
    import active from 'svelte-spa-router/active';
    const navItems = [
        {name: "About"},
        {name: "Skills"},
        {name: "Projects"},
        {name: "Contact"}
    ]
   
</script>

<style>
    nav {
        display:flex;
        justify-content:space-between;
        align-items: center;
        position: fixed;
        width: 100%;
        top:0;
        backdrop-filter: blur(2px);
        z-index: 1;
    }
    h1{
        font-size: 1.5rem;
        letter-spacing: 0.2rem;
        margin: 0.5rem;
        font-family: 'Open Sans', sans-serif;
        border-bottom: 2px solid #24d6ee;
    }
    ul {
        display: flex;
        margin: 0;
        padding: 0.5rem;
    }   
    li {
        list-style-type: none;
        background: none;  
        border: none;
        padding: 0 0 0.5rem 0;
        margin: 0.5rem 0.5rem 0 0.5rem;
        border-radius: 0;
        letter-spacing: 0.01rem;
        border-bottom: 2px solid transparent;
    }
    .link {
        padding-bottom: 0.5rem;
    }
    :global(a.active) {
        border-bottom: 2px solid #24d6ee;
    }

    
</style>

<nav>
    <a href="/" use:link ><h1>CB</h1></a>
    <ul>
        {#each navItems as item}
            <li>
                <a class="link" href={`/${item.name}`} use:link use:active={{path: `/${item.name}`, className: 'active'}}>{item.name}</a>
            </li>
        {/each}
    </ul>
</nav>