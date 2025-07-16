<script>
	let open = false;

	function togglePopup() {
		open = !open;
	}
</script>

<button id="credits-button" on:click={togglePopup} aria-label="Show credits" title="Show credits">
	<img src="/images/info.svg" alt="Info icon" />
</button>

<div class="credits-overlay" class:visible={open}>
	<p>All attributions and credits are available in the <a href="https://github.com/spacexplorer11/trafalgar-to-trenches#readme#Licenses" target="_blank">README</a>.</p>
	<button on:click={togglePopup} id="close-button" aria-label="Close credits" title="Close credits">
		<img src="/images/close.svg" alt="Close icon" />
	</button>
</div>

<style>
	#credits-button {
		position: fixed;
		top: 10px;
		left: 10px;
		background: none;
		border: none;
		cursor: pointer;
		width: clamp(36px, 5vmin, 48px);
		height: clamp(36px, 5vmin, 48px);
		padding: 4px;
		touch-action: manipulation;
		z-index: 1001;
	}

	#credits-button img {
		width: 100%;
		height: 100%;
		object-fit: contain;
		display: block;
	}

	.credits-overlay {
		position: fixed;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		padding: 1.5rem;
		border-radius: 8px;
		box-shadow: 0 4px 12px rgba(0,0,0,0.15);
		z-index: 1100;
		visibility: hidden;
		display: flex;
		flex-direction: column;
		max-width: 350px;
		width: 30vw;
		opacity: 0;
		transition: opacity 0.3s ease, visibility 0.3s ease;
		backdrop-filter: none;
		background-color: #f4e2cb;
		margin: auto;
	}

	.credits-overlay.visible {
		visibility: visible;
		opacity: 1;
		backdrop-filter: blur(8px);
	}

	@media (max-width: 480px) {
		.credits-overlay {
			padding: 1rem;
			max-width: 90vw;
			top: 15vh;
			bottom: auto;
			transform: translate(-50%, 0);
		}
	}

	#close-button {
		position: absolute;
		top: 5px;
		right: 10%;
		background: none;
		border: none;
		cursor: pointer;
		width: clamp(16px, 2vmin, 24px);
		height: clamp(16px, 2vmin, 24px);
		padding: 2px;
		touch-action: manipulation;
	}
</style>