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
        display:flex;
        justify-content:space-between;
        align-items: center;
        position: fixed;
        width: 100%;
        top:0;
        backdrop-filter: blur(1px);
    }

    h1{
        font-size: 1.5rem;
        letter-spacing: 0.2rem;
        margin: 0.5rem;
        font-family: 'Open Sans', sans-serif;
        border-bottom: 2px solid #24d6ee;
    }
    h1:hover {
        cursor: pointer;
    }
    ul {
        display: flex;
        margin: 0;
        padding: 0.5rem;
    }
    li {
        list-style-type: none;
    }
    button{
      background: none;  
      border: none;
      padding: 0 0 0.5rem 0;
      margin: 0.5rem 0.5rem 0 0.5rem;
      border-radius: 0;
      letter-spacing: 0.01rem;
      border-bottom: 2px solid transparent;
    }
    button:hover {
        cursor: pointer;
        color: #24d6ee;
    }
    .active{
        border-bottom: 2px solid #24d6ee;
    }
</style>

<nav>
    <h1 on:click={() => setPage("Landing")}>CB</h1>
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