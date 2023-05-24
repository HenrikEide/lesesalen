<script>
	import welcome from '$lib/images/april.png';
</script>

<h1>
	<div class="welcome">
		<img src={welcome} alt="Welcome, gentlemen" />
	</div>

	You fell for the<br />classic ruse
</h1>

<h2>
	Not 1st of April? Refer to <a
		target="_blank"
		href="https://newskit.social/articles/what-to-do-when-its-not-first-of-april">this</a
	>
</h2>

<style>
	.welcome {
		display: flex;
		align-items: center;
		margin-right: 15%;
		margin-left: 10%;
	}

	.welcome img {
		max-width: 100%;
		max-height: 100%;
		width: auto;
		height: auto;
	}
</style>
