<script>
</script>
<div id="content">
	<div id="trafalgar">
		<h1><em id="TrafalgarTitle">Trafalgar</em></h1>
	</div>
	<h1 id="to">to</h1>
	<div id="ww1">
		<h1><em id="TrenchesTitle">Trenches</em></h1>
	</div>
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
	}

	#ww1 {
		width: 50%;
		position: relative;
	}

	#TrenchesTitle {
		text-align: center;
	}
</style>