<script>
    const navItems = [
        {name: "About"},
        {name: "Skills"},
        {name: "Projects"},
        {name: "Contact"}
    ]
    export let page;
    const setPage = (newPage) => (page = newPage);
</script>

<style>
    nav {
        width: 100%;
        display:flex;
        justify-content:space-between;
        align-items: center;
    }
    h1{
        font-size: 1rem;
        margin:0;
    }
    h1:hover {
        cursor: pointer;
    }
    ul {
        display: flex;
        margin: 0;
        padding: 0;
    }
    li {
        list-style-type: none;
    }
    button{
      background: none;  
      border: none;
      border-radius: 0;
    }
    button:hover {
        cursor: pointer;
        color: #24d6ee;
    }
    .active{
        border-bottom: 1px solid black;
    }
</style>

<nav>
    <h1 on:click={() => setPage("Landing")}>Conor Beamish</h1>
    <ul>
        {#each navItems as item}
            <li>
                <button 
                    on:click={() => setPage(item.name)}
                    class:active="{page===item.name}"
                >
                    {item.name}
                </button>
            </li>
        {/each}
    </ul>
</nav>