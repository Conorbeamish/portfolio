<script>
    import { fade, fly } from 'svelte/transition';

    let projects = [
        {name: "Dungeons and Dragons Encounter",
        description:"This full stack applicaion is to help players of Dungeons and Dragons organise monster encounters. It uses the Open5e API allowing users to search for monsters and items and save them to encounters which they can quickly access during gameplay to see particluar stats and abilities. It is built using React and Redux with an Express server and MongoDB/Mongoose for storing user data/encounters.",
        img: "/images/dnd-encounter.png",
        tech:["React", "Redux", "Node/Express", "MongoDB"],
        url:"https://cb-dndencounter-client.herokuapp.com/",
        source: "https://github.com/Conorbeamish/dnd-encounter"
        },
        {name:"Image Analyser",
        description:"This app is built using React and AWS Rekognition with an Express backend server. Users can analyse images by linking to them online, the images are processed by Rekognition and a response is given with labels for the image and confidences for those labels.",
        tech: ["React", "AWS Rekognition", "Express"],
        img:"/images/image-analyser.png",
        url:"https://cb-image-analyser.herokuapp.com/",
        source:"https://github.com/Conorbeamish/rekognition-app-server"
        },
        {name:"Quiz App",
        description:"An applicaiton built with react that uses the Open Trivia DB API to generate trivia questions that uses can answers. The API is also controlled by a variety of parameters set by the user before the API call is made.",
        tech:["React", "OpenTriviaDB API"],
        img:"/images/quiz-app.png",
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
        {name:"This Portfolio",
        description:"This portfolio was built using Svelte, please click below if you would like to see how it works",
        tech:["", "Svelte", ""],
        img:"/images/portfolio.png",
        url:"/",
        source:"https://github.com/Conorbeamish/portfolio"
        }
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

    .project{
        display: flex;
        flex-direction: column;
        padding-bottom: 2rem;
        border-bottom: 2px solid #24d6ee;
        margin-bottom: 2rem;
    }
    .link-container{
        margin: 1rem auto 0 auto;
    }
    .project-link{
        border: 2px solid #24d6ee;
        padding: 0.25rem;
        margin: 1rem;
        transition: 0.3s ease all;
    }
    .project-link:hover{
        cursor: pointer;
        color: black;
        background: #24d6ee;
    }
    .project-img {
        border: 1px solid rgba(0, 0, 0, 0.25);
        max-width: 100%;
        object-fit: contain;
        transition: 0.5s ease;
        margin-bottom: 1rem;
    }
    .tech-list{
        margin: 0 auto 1rem auto;
    }
    .tech{
        display: inline;
        padding: 0 0.5rem 0 0.5rem;
    }
    .tech:not(:last-child){
        border-right: 2px solid #24d6ee;
    }
    h4 {
        margin-bottom: 0;
    }

    @media only screen and (min-width: 768px) {
        section{
            width: 60%;
        }
    }
</style>

<section in:fade="{{delay: 1000, duration:1000}}" out:fly="{{y:200, duration:1000}}">
    <h3>My Work</h3>
    <p>Bellow is a section of the projects I have worked on, some ongoing projects and more can be found <a href="https://github.com/Conorbeamish"><span>here</span></a>. You can see the working sites and view the code by hovering over the images below.</p> 
    <div class="project-container">
        {#each projects as project}
            <div class="project">
                <h4>{project.name}</h4>
                <p>{project.description}</p>
                <div class="tech-list">
                    {#each project.tech as tech}
                        <div class="tech">
                        {tech}
                        </div>
                    {/each}
                </div> 
                <img class="project-img" src={project.img} alt={`${project.name} Image`}/>
                <div class="link-container">
                    <a class="project-link" target="_blank" href={project.url}>View Site</a>
                    <a class="project-link" target="_blank" href={project.source}>View Code</a>
                </div>
            </div>
        {/each}
    </div>
</section>
