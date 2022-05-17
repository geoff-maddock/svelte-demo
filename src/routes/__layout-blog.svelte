<script>
	import Header from '$lib/header/Header.svelte';
	import '../app.css';
</script>

<nav>
	<div class="links">
		<a href="/blog">Blog</a>
	</div>
</nav>


<main>
	<slot />
</main>

<footer>
	<p>Copyright 2022 Geoffrey Maddock</p>
</footer>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
		background-color: #dfd1db;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
    .links {
        margin-left: auto;
    }

	nav {
		display: flex;
		align-items:center;
		max-width: 960px;
		margin: 0 auto;
	}
</style>
