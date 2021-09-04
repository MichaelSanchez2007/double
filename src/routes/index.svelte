<script>
	import Header from '$lib/Header.svelte';
	import StarA from '$lib/StarA.svelte';
	import AudioPlayer, { stopAll } from '$lib/AudioPlayer.svelte';
	import { fly, slide } from 'svelte/transition';
	import { onMount } from 'svelte';
	let audioTracks = ['/Paper.mp3'];

	let mounted = false;
	onMount(() => {
		mounted = true;
	});
</script>

{#each audioTracks as src}
	<AudioPlayer {src} />
{/each}

<div class="title">
	<h1>Discord.</h1>

	<hr />

	<div class="subtitle">
		<p>
			A great place to chat with friends, make calls, "Whats for homework" and meeting new people!
		</p>
	</div>
</div>

<div class="containerA">
	<h2>Review From Former Discord User</h2>
	<hr />
	<p>
		Holy moly guacamoly is this thing the most beautiful thing ive discovered! I have met new
		clients, new friends and have had so much fun using and navigating Discord! Discord is very new
		user friendly and even provides a tutorial on how to use it!
	</p>
	<div id="star"><StarA /></div>
</div>

<Header />

<div class="background" />

<style>
	#star {
		position: absolute;
		margin: auto;
		right: 0;
		left: 0;
		width: 200px;
		height: 50px;
		bottom: 10px;
		box-shadow: 0 1px 5px 1px rgba(0, 0, 0, 0.57);
		border-radius: 25px;
		text-align: center;
	}
	.containerA {
		background: rgb(0, 0, 0);
		width: 300px;
		height: 400px;
		border-radius: 35px;
		margin: auto;
		position: absolute;
		top: 0;
		right: 120px;
		bottom: -80px;
		box-shadow: -1px 1px 42px 7px rgba(0, 0, 0, 0.57);
		transition: 0.5s;
		animation: 10s infinite alternate hover;
		color: white;
		padding: 20px;
	}
	.container:hover {
		transform: scale(1.1);
	}
	h2 {
		padding: 20px;
		text-align: center;
	}
	hr {
		padding: 1px;
	}
	.title {
		width: 300px;
		height: 10px;
		position: absolute;
		margin: auto;
		right: 0;
		left: 0;
		color: white;
		text-align: center;
	}
	p {
		font-size: 20px;
	}
	h1 {
		text-align: center;
		position: relative;
	}
	.background {
		position: absolute;
		inset: 0;
		max-width: 100vw;
		max-height: 100vh;
		background-image: url('/Discord.jpg');
		background-repeat: no-repeat;
		background-size: cover;
		z-index: -1;
	}
	@media only screen and (max-width: 1000vw) {
		.background {
			height: 500vw;
		}
	}
	@keyframes hover {
		0% {
			transform: translateY(3%);
		}
		100% {
			transform: translateY(-3%);
		}
	}
</style>
