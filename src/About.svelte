<script>
    import { fade, fly } from 'svelte/transition';
</script>

<style>
    section{
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 1.25rem;
        min-height: 80vh;
    }
    .container{
        width: 80%;
        display: flex;
        flex-direction: column;
        justify-content: space-between
    }
</style>

<section out:fly="{{y:200, duration:1000}}">
    <div class="container">
        <h3 in:fly={{y:200, delay:1000, duration: 1000}}>About Me</h3>
        <p in:fly={{y:200, delay: 1500, duration: 1000}}>I graduated Cardiff University with a degree in Mathematics, Operational Research and Statistics</p>
        <p in:fly={{y:200, delay:2000, duration: 1000}}>After that I've spent time working in Canada, New Zealand, and Japan</p>
        <p in:fly={{y:200, delay:2500, duration: 1000}}>Now I live back in the UK and develop websites using modern technologies</p>
        <p in:fly={{y:200, delay:3000, duration: 1000}}>When I'm not coding, you'll find me rock climbing, skiing, or travelling</p>
    </div>
</section>
