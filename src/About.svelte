<script>
    import { fade, fly } from 'svelte/transition';
</script>

<style>
    section{
        width: 80%;
        min-height: 80vh;
        padding-top: 10vh;
        margin-left: auto;
        margin-right: auto;
    }
    .container{
        display: flex;
        flex-direction: column;
        justify-content: space-between
    }
    @media only screen and (min-width: 768px) {
        section{
            width: 60%;
            font-size: 1.25rem;
        }
    }
</style>

<section out:fly="{{y:200, duration:1000}}">
    <div class="container">
        <h3 in:fly={{y:200, delay:1000, duration: 1000}}>About Me</h3>
        <p in:fly={{y:200, delay: 1500, duration: 1000}}>I graduated Cardiff University with a degree in Mathematics, Operational Research and Statistics</p>
        <p in:fly={{y:200, delay:2000, duration: 1000}}>After that I've spent time working in Canada, New Zealand, and Japan</p>
        <p in:fly={{y:200, delay:2500, duration: 1000}}>Now I live back in the UK and develop websites & applications using modern technologies</p>
        <p in:fly={{y:200, delay:3000, duration: 1000}}>When I'm not coding, you'll find me rock climbing, skiing, or travelling</p>
    </div>
</section>
