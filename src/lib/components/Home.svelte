<script>
</script>

<button>
	<a href="/" aria-label="Home">
		<img src="/images/home.svg" alt="Button to return to the home page" title="Home button"/>
	</a>
</button>
<style>
	button {
		position: fixed;
		top: 10px;
		right: 10px;
		background: none;
		border: none;
		cursor: pointer;
		width: clamp(36px, 5vmin, 48px);
		height: clamp(36px, 5vmin, 48px);
		padding: 4px;
		touch-action: manipulation;
		z-index: 1001;
	}

	button img {
		width: 100%;
		height: 100%;
		object-fit: contain;
		display: block;
	}
</style>