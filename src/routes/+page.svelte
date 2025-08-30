<script>
	import {onMount, tick} from 'svelte';
	import {fade} from 'svelte/transition';

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

			<h1 id="TrafalgarTitle">
				<em>Trafalgar</em>
			</h1>
			<div class="image-wrapper">
				<a class="fake-link" href="/trafalgar" aria-label="Battle of Trafalgar information page"></a>
				<img src="/images/battle-of-trafalgar.jpg" alt="Battle of Trafalgar" aria-label="Battle of Trafalgar"
				     title="Battle of Trafalgar"/>
				<div class="overlay">
					<a href="/trafalgar" aria-label="Battle of Trafalgar information page">
						<button>More Information</button>
					</a>
				</div>
			</div>
		</div>
	{/if}

	{#if showTo}
		<h1 in:fade={{ duration: 1000 }} id="to">to</h1>
	{/if}

	{#if showTrenches}
		<div id="ww1" in:fade={{ duration: 1000 }}>
			<h1 id="TrenchesTitle">
				<em>Trenches</em>
			</h1>
			<div class="image-wrapper">
				<a class="fake-link" href="/ww1" aria-label="World War One information page"></a>
				<img src="/images/infantry-trenches.jpg" alt="Infantry Trenches" aria-label="Infantry Trenches"
				     title="Infantry Trenches"/>
				<div class="overlay">
					<a href="/ww1" aria-label="World War One information page">
						<button>More Information</button>
					</a>
				</div>
			</div>
		</div>
	{/if}
</div>
<div style="position: absolute; top: 30px; left: 10px; z-index: 10;">
	<iframe height="32" src="https://github.com/sponsors/Spacexplorer11/button" style="border: 0; border-radius: 6px;"
	        title="Sponsor Spacexplorer11" width="114"></iframe>
</div>
<div style="position: absolute; top: 10px; right: 10px; z-index: 10;">
	<a href="https://www.buymeacoffee.com/spacexplorer11" style="cursor: pointer;" target="_blank">
		<img alt="Buy Me A Coffee" src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png"
		     style="height: 60px !important;width: 217px !important;">
	</a>
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
		margin-top: 50px;
		min-height: 100vh;
	}

	#content a {
		text-decoration: none;
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

	#trafalgar .image-wrapper .fake-link:hover + img {
		transform: translateX(-100%);
	}

	/* World War 1 Section */

	#ww1 {
		width: 50%;
		position: relative;
		height: 95vh;
	}

	#ww1 .image-wrapper .fake-link:hover + img {
		transform: translateX(100%);
	}

	#TrenchesTitle {
		text-align: center;
	}

	/* Cool Animation stuff */

	/* Initially hide button */
	.overlay {
		position: absolute;
		bottom: 40%;
		left: 50%;
		transform: translateX(-50%);
		width: 60%;
		height: 25%;
		display: flex;
		justify-content: center;
		align-items: center;
		opacity: 0;
		transition: opacity 0.3s ease;
		z-index: 2;
		pointer-events: none;
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

	/* When hover zone hovered, show button */
	.fake-link:hover ~ .overlay {
		opacity: 1;
		pointer-events: auto;
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
		max-width: 100%;
		height: auto;
		display: block;
		cursor: pointer;
		pointer-events: none; /* Make button non-interactive */
	}

	.overlay button:hover {
		transform: scale(1.05);
	}

	/* The fake-link covers the hover zone area and is transparent */
	.fake-link {
		position: absolute;
		bottom: 40%;
		left: 50%;
		transform: translateX(-50%);
		width: 100%;
		height: 25%;
		cursor: pointer;
		background: transparent;
		z-index: 3;
		display: block;
		opacity: 0;
		pointer-events: auto;
	}

</style>
