<script>
    import { fade, fly } from 'svelte/transition';
</script>

<style>
    section{
        min-height: 80vh;
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
    }
    .container{
        font-size: 2rem;
        top: 50%;
        display: flex;
        flex-direction: column;
        width: 50%;
        margin-left: auto;
        margin-right: auto;
    }
    .text{
        font-weight: 200;
    }
   
</style>

<section out:fly="{{y:200, duration:1000}}">
    <div class="container">
        <div in:fade={{delay: 1000, duration: 1000}}>Hello I'm</div>
        <h3 in:fade={{delay: 1500, duration: 1000}}>Conor Beamish</h3>
        <div in:fade={{delay: 2000, duration: 1000}} class="text">A Web Developer based in Cardiff, Wales</div>
    </div>
 
</section>