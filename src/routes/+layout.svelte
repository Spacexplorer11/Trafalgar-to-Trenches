<script>
import Info from '$lib/Info.svelte';
</script>

<div class="national-park">
<slot/>
<Info/>
</div>
<style>
	@import url('https://fonts.googleapis.com/css2?family=National+Park:wght@200..800&display=swap');
	.national-park {
		                font-family: "National Park", sans-serif;
		                font-optical-sizing: auto;
		                font-weight: 800;
		                font-style: normal;
	                }
</style>
