<script>
    export let progress = 20;
</script>

<style>
    /* your styles go here */
    .progress-container {
        display: block;
        background: #ffffff;
        border: 1px solid coral;
        max-width: 460px;
        height: 32px;
        margin-bottom: 16px;
        padding: 0;
    }
    .progress-bar {
        display: block;
        margin: 0;
        padding: 0;
        height: 32px;
        background-color: coral;
    }
</style>
<div class="progress-container">
    <div class="progress-bar" style="width:{progress}%"></div>
</div>