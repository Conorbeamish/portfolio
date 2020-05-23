<script>
    let projects = [
        {name:"Fallout Minigame",
        description:"A clone of the fallout hacking terminal game, made with vanilla js.",
        tech:["Javascript", "CSS", "HTML"],
        img:"/images/fallout-minigame.png",
        url:"https://conorbeamish.github.io/fallout-minigame/index.html",
        source:"https://github.com/Conorbeamish/fallout-minigame"}
    ]
</script>

<style>
    img {
        width: 10%;
    }
    a:hover{
        cursor: pointer;
    }
    .tech{
        display: inline;
    }
</style>

<h3>My Work</h3>

<div>
    {#each projects as project}
        <h4>{project.name}</h4>
        <p>{project.description}</p>
        <div>
            {#each project.tech as tech}
                <div class="tech">
                    {tech}
                </div>
            {/each}
        </div>
        <img src={project.img} alt={`${project.name} Image`}/>
        <a target="_blank" href={project.url}><img src="/images/computer.svg" alt="Link to site"/></a>
        <a target="_blank" href={project.source}><img src="/images/coding.svg" alt="Link to source code"/></a>
    {/each}
</div>