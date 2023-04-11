<script>
	import welcome from '$lib/images/april.png';
</script>

<h1>
	<span class="welcome">
		<picture>
			<img src={welcome} alt="Welcome, gentlemen" />
		</picture>
	</span>

	You fell for the<br />classic ruse
</h1>

<h2>
	Not 1. April? Refer to <a
		target="_blank"
		href="https://newskit.social/articles/what-to-do-when-its-not-first-of-april">this</a
	>
</h2>

<style>
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
