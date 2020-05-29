<script>
    import { fade, fly } from 'svelte/transition';
    let formData = {
        email: "",
        name: "",
        subject: "",
        message: ""
    }
    const handleSubmit = () => {
        fetch("https://formspree.io/mbjzgbde", {
            method: "POST",
            headers: {
          "Content-Type": "application/json",
          Accept: "application/json",
        },
        body: JSON.stringify(formData),
        })
        .then((res) => res.json())
        .catch((err) => console.log(err))
    }
</script>

<style>
    section{
        padding-top: 10vh;
        width: 80%;
        margin-left: auto;
        margin-right: auto;
    }
    form{
        padding: 2rem;
        width: 80%;
        background-color: #d3d3d3;
    }
    div {
        position: relative;
    
    }
    label{
        margin-left: 0.5rem;
        position: absolute;
        top: 0;
        pointer-events: none;
        transition: 0.2s ease all;
    }
    input{
        padding-top: 1rem;
        width: 100%;
        border-radius: 0.25rem;
    }
    input:focus ~ label {
        font-size: 0.75rem;
        color: #24d6ee;
    }
    textarea{
        padding-top: 1rem;
        width: 100%;
        height: 40vh;
        border-radius: 0.25rem;
    }
    textarea:focus ~ label {
        font-size: 0.75rem;
        color: #24d6ee;
    }
    button{
        transition: .3s;
        border-radius: 0.25rem;
    }
    button:hover{
        cursor: pointer;
        background-color: #24d6ee;
    }
</style>

<section in:fade="{{delay: 1000, duration:1000}}" out:fly="{{y:200, duration:1000}}">
    <h3>Contact</h3>
    <p>If you want to get in contact please complete the form below...</p>
    <form 
        on:submit|preventDefault={handleSubmit} 
    >
        <div>
            <input type="text" name="name" autocomplete="off"  bind:value={formData.name}>
            <label for="name">Name</label>
        </div>
        <div>
            <input type="email" name="email" autocomplete="off" bind:value={formData.email}>
            <label for="email">Email Address</label>
        </div>  
        <div>
            <input type="text" name="subject" autocomplete="off"  bind:value={formData.subject}>
            <label for="subject">Subject</label>
        </div>
        <div>
            <textarea name="message"  autocomplete="off" bind:value={formData.message}></textarea>
            <label for="message">Message</label>
        </div>
        <button type="submit">Send</button>
    </form>
</section>
