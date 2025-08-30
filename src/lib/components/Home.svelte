<script>
</script>

<button>
	<a aria-label="Home" href="/">
		<img alt="Button to return to the home page" src="/images/home.svg" title="Home button"/>
	</a>
</button>
<style>
	button {
		position: fixed;
		top: -5px;
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