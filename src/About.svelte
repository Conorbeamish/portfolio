<script>
    import { fade, fly } from 'svelte/transition';
</script>

<style>
    section{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        font-size: 1.25rem;
    }
    .container{
        width: 80%;
    }
   
</style>

<section in:fade={{delay:1000, duration: 1000}} out:fly="{{y:200, duration:1000}}">
    <div class="container">
        <h3>About Me</h3>
        <p>I graduated Cardiff University with a degree in Mathematics, Operational Research and Statistics</p>
        <p>After that I've spent time working in Canada, New Zealand, and Japan</p>
        <p>Now I live back in the UK and develop websites using modern technologies.</p>
        <p>When I'm not coding, you'll find me rock climbing, skiing, or travelling.</p>
    </div>
</section>
