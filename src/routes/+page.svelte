<script>
	import welcome from '$lib/images/april.png';
</script>

<svelte:head>
	<title>Lesesalen</title>
	<meta name="description" content="Lesesalen webpage" />
</svelte:head>

<section>
	<h1>
		<span class="welcome">
			<picture>
				<img src={welcome} alt="Welcome, gentlemen" />
			</picture>
		</span>

		You fell for the<br />classic ruse
	</h1>

	<h2>Happy Easter!</h2>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 25%;
		margin-left: auto;
		margin-right: auto;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
