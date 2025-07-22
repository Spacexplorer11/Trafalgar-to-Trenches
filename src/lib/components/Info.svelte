<script>
	let open = false;

	function togglePopup() {
		open = !open;
	}
</script>

<button aria-label="Show credits" id="credits-button" on:click={togglePopup} title="Show credits">
	<img alt="Info icon" src="/images/info.svg"/>
</button>

<div class="credits-overlay" class:visible={open}>
	<p>All attributions and credits are available in the <a
			href="https://github.com/spacexplorer11/trafalgar-to-trenches#readme#Licenses" target="_blank">README</a>.
	</p>
	<button aria-label="Close credits" id="close-button" on:click={togglePopup} title="Close credits">
		<img alt="Close icon" src="/images/close.svg"/>
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
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
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
		right: 2%;
		background: none;
		border: none;
		cursor: pointer;
		width: clamp(32px, 5vmin, 48px);
		height: clamp(32px, 5vmin, 48px);
		padding: 2px;
		touch-action: manipulation;
	}

	#close-button img {
		width: 100%;
		height: 100%;
		object-fit: contain;
		display: block;
	}
</style>