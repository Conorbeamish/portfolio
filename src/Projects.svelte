<script>
    import { fade, fly } from 'svelte/transition';

    let projects = [
        {name: "Dungeons and Dragons Encounter",
        description:"This applicaion is to help players of Dungeons and Dragons organise monster encounters. It uses the Open5e API allowing users to search for monsters and items and save them to encounters which they can quickly access during gameplay to see particluar stats and abilities. It is built using React and Redux with an Express server and MongoDB/Mongoose for storing user data/encounters.",
        img: "",
        tech:["React", "Redux", "Node/Express", "MongoDB"],
        url:"https://cb-dndencounter-client.herokuapp.com/",
        source: "https://github.com/Conorbeamish/dnd-encounter"
        },
        {name:"Image Analyser",
        description:"This app is built using React and AWS Rekognition with an Express backend server. Users can analyse images by linking to them online, the images are processed by Rekognition and a response is given with labels for the image and confidences for those labels.",
        tech: ["React", "AWS Rekognition", "Express"],
        img:"",
        url:"https://cb-image-analyser.herokuapp.com/",
        source:"https://github.com/Conorbeamish/rekognition-app-server"
        },
        {name:"Quiz App",
        description:"An applicaiton built with react that uses the Open Trivia DB API to generate trivia questions that uses can answers. The API is also controlled by a variety of parameters set by the use before the API call is made. This project is hosted on Herkou so please allow a moment for it to load.",
        tech:["React"],
        img:"",
        url: "https://cb-quiz-app.herokuapp.com/",
        source: "https://github.com/Conorbeamish/quiz-app"
        },
        {name:"Fallout Minigame",
        description:"A clone of the fallout hacking terminal game, made with vanilla Javascript, CSS and HTML. This is a simple responsive application built with accesibility in mind.",
        tech:["Javascript", "CSS", "HTML"],
        img:"/images/fallout-minigame.png",
        url:"https://conorbeamish.github.io/fallout-minigame/index.html",
        source:"https://github.com/Conorbeamish/fallout-minigame"
        },
    ]
</script>

<style>
    section{
        width: 80%;
        padding-top: 10vh;
        padding-bottom: 10vh;
        margin-left: auto;
        margin-right: auto;
    }
    img {
        width: 10%;
    }
    a:hover{
        cursor: pointer;
    }
    .project-container{

    }
    .project{
        display: flex;
        flex-direction: column;

    }
    .tech{
        display: inline;
        padding: 0 0.5rem 0 0.5rem;
    }
    .tech:not(:last-child){
        border-right: 2px solid #24d6ee;
    }
</style>

<section in:fade="{{delay: 1000, duration:1000}}" out:fly="{{y:200, duration:1000}}">
    <h3>My Work</h3>

    <div class="project-container">
        {#each projects as project}
            <div class="project">
                <h4>{project.name}</h4>
                <div class="tech-list">
                    {#each project.tech as tech}
                        <div class="tech">
                        {tech}
                        </div>
                    {/each}
                </div>
                <p>{project.description}</p>
                <img src={project.img} alt={`${project.name} Image`}/>
                <div>
                    <a target="_blank" href={project.url}><img src="/images/computer.svg" alt="Link to site"/></a>
                    <a target="_blank" href={project.source}><img src="/images/coding.svg" alt="Link to source code"/></a>
                </div>
            </div>
        {/each}
        <div>
            This portfolio was built using Svelte, you can view the code <a href="https://github.com/Conorbeamish/portfolio">here</a>
        </div>
    </div>
</section>
