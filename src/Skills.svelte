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
        padding-top: 10vh;
        display: flex;
        flex-direction: column;
        width: 80%;
        min-height: 70vh;
        margin-left: auto;
        margin-right: auto;
    }
    .skill-list{

        display: flex;
        justify-content: space-evenly;
        flex-wrap: wrap;
    }

    p{
        margin-top: 0;
    }
    h4{
        text-align: center;
        margin-bottom: .5rem;
    }
    @media only screen and (min-width: 768px) {
        section{
            width: 60%;
            font-size: 1.25rem;
        }
    }
</style>

<section  out:fly="{{y:200, duration:1000}}">
    <h3 in:fly={{y:200, delay:1000, duration: 2000}}>Skills</h3>
    <p in:fly={{y:200, delay:1500, duration: 2000}}>
        I am a self taught developer and have experience using technologies including...
    </p>
    <div in:fly={{y:200, delay:2000, duration: 2000}} class="skill-list">
        {#each skills as skill}
        <div class="skill">
            <h4>{skill.name}</h4>
            <img src={`/images/${skill.name}.png`} alt={`${skill.name} Logo`}>
        </div>
        {/each}
    </div>
</section>
