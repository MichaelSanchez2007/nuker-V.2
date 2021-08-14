<script>
	import FlashyText from '../components/FlashyText.svelte';

	let showNuke, showNukePage, audio, nukePage;

	function nuke() {
		showNuke = true
		audio.currentTime = 1
		audio.play()
		setTimeout(() => {
			showNukePage = true;
			setTimeout(() => {
				nukePage.style.animationDuration = '272.5ms'
			}, 17450)
		}, 8730)
	}

	function supernuke() {
		window.close();
	}
</script>

<h1>Nuker</h1>

<button on:click={nuke}>nuke button</button>
<br />
<br />
<button on:click={supernuke}>Super nuke button</button>

{#if showNuke == true}
	<img src="https://media.giphy.com/media/oe33xf3B50fsc/giphy.gif" alt="nuke"/>
	<FlashyText />
{/if}

{#if showNukePage == true}
	<div bind:this={nukePage} class="nukepage" />
{/if}

<audio bind:this={audio} style="visibility: hidden" preload="auto">
	<source src="/bangarang.mp3" type="audio/mp3">
</audio>

<style>
	.nukepage {
		position: fixed;
		inset: 0;
		width: 100vw;
		height: 100vh;
		animation: 545ms linear infinite nuke;
	}
	@keyframes nuke {
		0% {
			background: red;
		}
		29.9% {
			background: red;
		}
		30% {
			background: black;
		}
		99.9% {
			background: black;
		}
	}
	img {
		width: 100vw;
		position: fixed;
		inset: 0;
	}
	h1 {
		text-align: center;
		color: blue;
	}
	button {
		cursor: pointer;
		background: tomato;
		color: black;
		text-transform: uppercase;
		outline: none;
		border: none;
		width: max-content;
		border-radius: 5px;
		padding: 3px 7px;
		margin: auto;
		display: flex;
	}
</style>
