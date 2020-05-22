<script>
    // your script goes here
    import AppProgressBar from './AppProgressBar.svelte';

</script>

<style>
    /* your styles go here */
    button {
        color: #ffffff;
        background-color: lightcoral;
        border: 1px solid coral;
        border-radius: 3px;
    }
</style>

<h3>Seconds left to pet a Tuxedo Cat! :D</h3>
<div>
    <AppProgressBar />

    <button on:click="">Start petting</button>
</div>
