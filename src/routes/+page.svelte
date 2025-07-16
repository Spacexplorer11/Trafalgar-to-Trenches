<script>
	import { onMount, tick } from 'svelte';
	import { fade } from 'svelte/transition';

	let showTrafalgar = false;
	let showTo = false;
	let showTrenches = false;

	onMount(async () => {
		showTrafalgar = true;
		await tick();
		await new Promise(res => setTimeout(res, 500));

		showTo = true;
		await tick();
		await new Promise(res => setTimeout(res, 500));

		showTrenches = true;
	});
</script>
<div id="content">
	{#if showTrafalgar}
		<div id="trafalgar" in:fade={{ duration: 1000 }}>
			<h1>
				<em id="TrafalgarTitle">Trafalgar</em>
			</h1>
			<img src="/images/battle-of-trafalgar.jpg" alt="Battle of Trafalgar" aria-label="Battle of Trafalgar" title="Battle of Trafalgar" />
		</div>
	{/if}

	{#if showTo}
		<h1 in:fade={{ duration: 1000 }} id="to">to</h1>
	{/if}

	{#if showTrenches}
		<div id="ww1" in:fade={{ duration: 1000 }}>
			<h1>
				<em id="TrenchesTitle">Trenches</em>
			</h1>
			<img src="/images/infantry-trenches.jpg" alt="Infantry Trenches" aria-label="Infantry Trenches" title="Infantry Trenches" />
		</div>
	{/if}
</div>
<style>
	#content::before {
		content: "";
		top: 0;
		bottom: 0;
		left: 50%;
		width: 2px;
		background: black;
		transform: translateX(-50%);
		z-index: 1;
		position: absolute;
	}

	#to {
		position: absolute;
		text-align: center;
		top: 2.5%;
		letter-spacing: 3px;
		left: 50.2%;
		transform: translate(-50%, -50%);
		color: black;
		z-index: 2;
	}

	#TrafalgarTitle {
		text-align: center;
	}

	#content {
		display: flex;
		flex-direction: row;
		position: relative;
		min-height: 100vh;
	}

	#trafalgar {
		width: 50%;
		position: relative;
		height: 95vh;
	}

	#trafalgar img {
		max-width: 100%;
		height: auto;
		display: block;
	}

	#ww1 {
		width: 50%;
		position: relative;
		overflow: hidden;
		height: 95vh;
	}

	#ww1 img {
		max-width: 100%;
		width: 100%;
		height: 100%;
		display: block;
		object-fit: cover;
	}

	#TrenchesTitle {
		text-align: center;
	}
</style>