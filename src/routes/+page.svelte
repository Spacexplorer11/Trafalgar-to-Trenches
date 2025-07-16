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
			<div class="image-wrapper">
				<img src="/images/battle-of-trafalgar.jpg" alt="Battle of Trafalgar" aria-label="Battle of Trafalgar" title="Battle of Trafalgar" />
				<div class="overlay">
					<button>More Information</button>
				</div>
			</div>
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
			<div class="image-wrapper">
				<img src="/images/infantry-trenches.jpg" alt="Infantry Trenches" aria-label="Infantry Trenches" title="Infantry Trenches" />
				<div class="overlay">
					<button>More Information</button>
				</div>
			</div>
		</div>
	{/if}
</div>
<style>

	/* Content Styles */

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

	#content {
		display: flex;
		flex-direction: row;
		position: relative;
		min-height: 100vh;
	}

	/* To */

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

	/* Trafalgar Section */

	#TrafalgarTitle {
		text-align: center;
	}

	#trafalgar {
		width: 50%;
		position: relative;
		height: 95vh;
	}

	/* World War 1 Section */

	#ww1 {
		width: 50%;
		position: relative;
		height: 95vh;
	}

	.image-wrapper {
		position: relative;
		width: 100%;
		height: 100%;
		overflow: hidden;
	}

	.image-wrapper img {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		object-fit: cover;
		transition: transform 0.4s ease;
		z-index: 2;
		display: block;
	}

	#trafalgar .image-wrapper:hover img {
		transform: translateX(-100%);
	}

	#ww1 .image-wrapper:hover img {
		transform: translateX(100%);
	}

	.overlay {
		position: absolute;
		inset: 0;
		display: flex;
		justify-content: center;
		align-items: center;
		z-index: 1;
	}

	.overlay button {
		padding: 0.75rem 1rem;
		background: #508364;
		color: white;
		font-size: 1rem;
		text-align: center;
		transition: transform 0.3s ease;
		border: 2px solid black;
		border-radius: 5px;
		width: 100%;
		max-width: 300px;
		display: block;
		cursor: pointer;
	}

	.overlay button:hover {
		transform: scale(1.05);
	}

	#TrenchesTitle {
		text-align: center;
	}

</style>