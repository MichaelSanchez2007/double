<script context="module">
	const players = new Set();

	export function stopAll() {
		players.forEach((p) => p.pause());
	}
</script>

<script>
	import { onMount } from 'svelte';

	export let src;

	let player;

	onMount(() => {
		// Like players.push(player)
		players.add(player);
	});
</script>

<div class="container">
	<div class="background" />
	<h2>Sponsored by Paper Skies</h2>
	<hr />
	<p>
		This is one of Paper Skies greatest songs, you should go check him out! Did you know that Paper
		Skies is soon to become one of the most popular dubstep/edm artist in the world? It's not too
		late to become an OG.
	</p>

	<br />

	<div class="Button">
		<audio bind:this={player} {src} controls>
			<track kind="captions" />
		</audio>
	</div>
</div>

<img src="/Logo.png" alt="" />

<style>
	img {
		position: absolute;
		margin: auto;
		top: 400px;
		right: 880px;
		bottom: 0;
		left: 0;
		border-radius: 25px;
		box-shadow: 1px 2px 36px 11px rgba(0, 0, 0, 0.41);
		animation: 8.5s infinite alternate hover;
	}
	.container {
		background: rgb(0, 0, 0);
		width: 300px;
		height: 400px;
		border-radius: 35px;
		margin: auto;
		position: absolute;
		top: 0;
		right: 1400px;
		bottom: -80px;
		box-shadow: -1px 1px 42px 7px rgba(0, 0, 0, 0.57);
		transition: 0.5s;
		color: white;
		padding: 20px;
		animation: 10s infinite alternate hover;
		cursor: default;
	}
	p {
		font-size: 21px;
	}
	.Button {
		margin: 10px -10px auto;
		display: flex;
		width: 250px;
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
