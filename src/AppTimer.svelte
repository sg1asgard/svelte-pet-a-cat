<script>
    // your script goes here
    import AppProgressBar from './AppProgressBar.svelte';
    const totalSeconds = 5;
    let secondsLeft = totalSeconds;
    let isRunning = false;

    function startTimer() {
        isRunning = true;
        if (secondsLeft == 0) {
            secondsLeft = totalSeconds;
        }
        const timer = setInterval(() => {
            secondsLeft -= 1;
            if (secondsLeft == 0) {
                clearInterval(timer);
                isRunning = false;
            }
        }, 1000);
    }


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

<h3>{secondsLeft} left to pet a Tuxedo Cat! :D</h3>
<div>
    <AppProgressBar />

    <button disabled={isRunning} on:click="{startTimer}">Start petting</button>
</div>
