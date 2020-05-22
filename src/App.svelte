<script>
import AppHowTo from './AppHowTo.svelte';
import AppTimer from './AppTimer.svelte';

let appaudio;

function secondsLeft() {
	console.log('console log Svelte works');
}

function catPurring(e) {
	// console.log(e);
	appaudio.play();
}
</script>

<style>
	.container {
		padding: 32px;
	}
	h1 {
		color: coral;
		font-size: 3.2rem;
		padding: 0;
		margin: 0;
	}
	.iconapp {
		display: inline-block;
		max-width: 52px;
		vertical-align: middle;
	}
</style>
<div class="container">
	<h1>Pet A Cat App. <img class="iconapp" src="cat-icon.jpg" alt="Pet a Cat App." /></h1>

	<AppTimer />

	<AppHowTo on:catpurr="{catPurring}" />

	<audio bind:this="{appaudio}">
		<source src="cat-sounds/purring-cat.mp3">
		Your browser does not support the audio tag.
	</audio>
</div>