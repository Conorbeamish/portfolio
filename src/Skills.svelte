<script>  
    import { fade, fly } from 'svelte/transition';
    let skills = [
        {name: "Javascript"},
        {name: "CSS"},
        {name: "HTML"},
        {name: "React"},
        {name: "Redux"},
        {name: "Bootstrap"},
        {name: "jQuery"},
        {name: "Svelte"},
        {name: "Node"},
        {name: "MongoDB"},
    ]
    let fadeTime = 1000
</script>

<style>
    section {
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        width: 80%;
        margin-left: auto;
        margin-right: auto;
    }
    .skill-list{
        display: flex;
        justify-content: space-evenly;
        flex-wrap: wrap;
    }
    
    h3{
        font-size: 1.5rem;
    }
    p{
        font-size: 1.25rem;
    }
    h4{
        text-align: center;
        margin-bottom: .5rem;
    }
</style>

<section in:fade={{delay:1000, duration: 1000}} out:fly="{{y:200, duration:1000}}">
    <h3>Skills</h3>
    <p>I have...</p>
    <div class="skill-list">
        {#each skills as skill}
        <div class="skill">
            <h4>{skill.name}</h4>
            <img src={`/images/${skill.name}.png`} alt={`${skill.name} Logo`}>
        </div>
        {/each}
    </div>
</section>
