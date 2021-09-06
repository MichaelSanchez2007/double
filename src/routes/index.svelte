<script>
	import AudioPlayer from '$lib/AudioPlayer.svelte';
	import { fly } from 'svelte/transition';
	import Header from '$lib/Header.svelte';
	import StarA from '$lib/StarA.svelte';
	import { onMount } from 'svelte';
	let audioTracks = ['/Paper.mp3'];

	let mounted = false;
	onMount(() => {
		mounted = true;
	});
</script>

<div class="background" />

<div class="title">
	{#if mounted}
		<h1 class="discord">
			{#each 'Discord.' as letter, i}
				<div class="letter" in:fly={{ y: 10, delay: 150 * i }}>{letter}</div>
			{/each}
		</h1>

		<hr />

		<div class="subtitle">
			<p in:fly={{ y: 10, delay: 1250, duration: 1000 }}>
				A great place to chat with friends, make calls, "Whats for homework" and meeting new people!
			</p>
		</div>
	{/if}
</div>

<section>
	<div class="container-b">
		{#each audioTracks as src}
			<AudioPlayer {src} />
		{/each}
	</div>

	<div class="container-a">
		<h2>Review From Former Discord User</h2>
		<hr />
		<p>
			Holy moly guacamoly is this thing the most beautiful thing ive discovered! I have met new
			clients, new friends and have had so much fun using and navigating Discord! Discord is very
			new user friendly and even provides a tutorial on how to use it!
		</p>
		<div id="star"><StarA /></div>
	</div>
</section>

<Header />

<style>
	section {
		display: flex;
		justify-content: space-between;
		max-width: min(80vw, 1500px);
		margin: auto;
		align-items: center;
		position: relative;
		flex-wrap: wrap;
		gap: 2rem;
	}
	@media (max-width: 875px) {
		section {
			justify-content: center;
		}
	}
	.letter {
		transition: 0.2s;
	}
	.letter:hover {
		color: rgb(114, 191, 221);
	}
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
		animation: 10s infinite rainbow;
		transition: 0.5s;
	}
	#star:hover {
		transform: scale(1.2);
	}
	.container-a {
		background: rgb(0, 0, 0);
		max-width: 300px;
		height: 400px;
		border-radius: 35px;
		/* margin: auto; */
		position: relative;
		box-shadow: -1px 1px 42px 7px rgba(0, 0, 0, 0.57);
		transition: 0.5s;
		animation: 10s infinite alternate hover;
		color: white;
		padding: 20px;
		cursor: default;
	}
	h2 {
		padding: 20px;
		text-align: center;
		cursor: default;
	}
	hr {
		padding: 1px;
	}
	.title {
		padding-top: 1rem;
		width: 300px;
		height: 162px;
		position: relative;
		margin: auto;
		right: 0;
		left: 0;
		color: rgb(255, 255, 255);
		text-align: center;
	}
	p {
		font-size: 20px;
		cursor: default;
	}
	h1 {
		text-align: center;
		position: relative;
		cursor: default;
		color: rgb(255, 255, 255);
		display: flex;
		justify-content: center;
		letter-spacing: 5px;
		margin: 0;
	}
	.background {
		position: absolute;
		inset: 0;
		max-width: 100vw;
		max-height: 100vh;
		background-image: url('/Discord.jpg');
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
		/* z-index: 0; */
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
	@keyframes rainbow {
		0% {
			filter: hue-rotate(0deg);
		}
		100% {
			filter: hue-rotate(360deg);
		}
	}
</style>
