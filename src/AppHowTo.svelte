<script>
    import { createEventDispatcher } from 'svelte';
    const appdispatcher = createEventDispatcher();
    
    function playCatSound() {
        // event.preventDefault();
        appdispatcher('catpurr', 'cat-purring');
    }

    let cats = [
        { catUrl: 'cat-to-pet-01' },
        { catUrl: 'cat-to-pet-02' },
        { catUrl: 'cat-to-pet-03' },
        { catUrl: 'cat-to-pet-04' },
        { catUrl: 'cat-to-pet-05' },
        { catUrl: 'cat-to-pet-06' },
        { catUrl: 'cat-to-pet-07' },
        { catUrl: 'cat-to-pet-08' },
        { catUrl: 'cat-to-pet-09' },
    ]
</script>
<style>
    /* your styles go here */
    .pets-container {
        margin-top: 32px;
        max-width: 560px;
    }
    img {
        display: inline-block;
        border-radius: 4px;
        max-width: 100%;
    }
</style>

<div class="pets-container">
    <div bp="grid 4">
        {#each cats as cat, i}
            <div>
                <img on:click="{playCatSound}" src="cat-images/{cat.catUrl}.jpg" alt="Pet a Cat" />
            </div>
        {/each}
    </div>
</div>