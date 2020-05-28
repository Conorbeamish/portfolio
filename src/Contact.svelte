<script>
    import { fade, fly } from 'svelte/transition';
</script>

<style>
    section{
        padding-top: 10vh;
        width: 80%;
        margin-left: auto;
        margin-right: auto;
    }
</style>

<section in:fade="{{delay: 1000, duration:1000}}" out:fly="{{y:200, duration:1000}}">
    <h3>Contact</h3>
    <form>
    
    </form>
</section>
