<script>
    // your script goes here
    import AppProgressBar from './AppProgressBar.svelte';
    const totalSeconds = 20;
    let secondsLeft = totalSeconds;
    let isRunning = false;
    $: progress = ((totalSeconds - secondsLeft) / totalSeconds) * 100;

    // Start Timer to pet a Cat.
    function startTimer() {
        // Set timer running as true, use it to disable the button while true
        isRunning = true;

        // run then timer countdown
        const timer = setInterval(() => {
            secondsLeft -= 1;
            if (secondsLeft == 0) {
                // stop the timer running
                clearInterval(timer);
                // enable the button for click
                isRunning = false;
                // if yes then reset the timer
                secondsLeft = totalSeconds;
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
        cursor: pointer;
    }
    button:hover {
        background-color: #db6e6e;
    }
    button[disabled] {
        color: #998585;
        background-color: #e1c5c5;
        border: 1px solid lightcoral;
        cursor: no-drop;
    }
</style>

<h3>{secondsLeft} seconds left to pet a Cat! :D</h3>
<div>
    <AppProgressBar {progress} />

    <button disabled={isRunning} on:click="{startTimer}">Start petting</button>
</div>
