<script>
	import './styles.css';
</script>

<svelte:head>
	<title>Lesesalen</title>
	<meta name="description" content="Lesesalen webpage" />
</svelte:head>

<div class="app">
	<main>
		<nav>
			<a href="/">Home</a>
			<a href="https://eiden.no/lesesalen/">Lesesalen</a>
			<a href="https://eiden.no/lesesalen/quiz">Quiz</a>
		</nav>
		<section>
			<slot />
		</section>
	</main>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}

	nav {
		display: flex;
		justify-content: left;
		align-items: center;
	}

	nav a {
		padding: 0.5rem;
		color: #2f4f4f;
	}

	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}
</style>
