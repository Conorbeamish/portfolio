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
        description:"An applicaiton built with react that uses the Open Trivia DB API to generate trivia questions that uses can answers. The API is also controlled by a variety of parameters set by the user before the API call is made. This project is hosted on Herkou so please allow a moment for it to load.",
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
    a:hover{
        cursor: pointer;
    }
    .project{
        display: flex;
        flex-direction: column;
        padding-bottom: 2rem;
        border-bottom: 2px solid #24d6ee;
        margin-bottom: 2rem;
    }
    .project-img {
        max-width: 100%;
        object-fit: contain;
        transition: 0.5s ease;
    }
    .img-container{
        position: relative;
        width: 100%;
    }
    .img-container:hover > .project-img {
        opacity: 0.3;
    }
    .img-container:hover > .icon-container{
        opacity: 1;
    }
    .icon-container{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        -ms-transform: translate(-50%, -50%);
        opacity: 0;
        transition: 0.5s ease;
    }
    .icon{
        width: 10vw;
        margin: 0 2rem 0 2rem;
    }
    .icon:focus{
        border: 1px solid #24d6ee;
    }
    .tech-list{
        margin-left: auto;
        margin-right: auto;
    }
    .tech{
        display: inline;
        padding: 0 0.5rem 0 0.5rem;
    }
    .tech:not(:last-child){
        border-right: 2px solid #24d6ee;
    }

    @media only screen and (min-width: 768px) {
        section{
            width: 60%;
        }
        .icon{
            width: 5vw;
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
                <div class="tech-list">
                    {#each project.tech as tech}
                        <div class="tech">
                        {tech}
                        </div>
                    {/each}
                </div>
                <p>{project.description}</p>
                <div class="img-container">
                    <img class="project-img" src={project.img} alt={`${project.name} Image`}/>
                    <div class="icon-container">
                        <a target="_blank" href={project.url}><img class="icon" src="/images/computer.svg" alt="Link to site"/></a>
                        <a target="_blank" href={project.source}><img class="icon" src="/images/coding.svg" alt="Link to source code"/></a>
                    </div>
                </div>
            </div>
        {/each}
    </div>
</section>
