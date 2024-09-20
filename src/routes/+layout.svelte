<script lang="ts">
	import Menu from '../components/Menu.svelte';
</script>

<header>
	<h1>
		<a href="/">ALI GROUP</a>
	</h1>
	<Menu />
</header>

<main>
	<slot />
</main>

<footer>
	<p>© 2023 ALI GROUP. All rights reserved.</p>
</footer>

<style>
	header {
		background: #0f4c75;
		padding: 1rem;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
		display: flex;
		justify-content: space-between;
		align-items: center;
		position: sticky;
		top: 0px;
		z-index: 100;
		height: 80px;
	}

	h1 {
		margin: 0;
		font-size: 2rem;
		padding-left: 30px;
	}

	h1 a {
		color: #fff;
		text-decoration: none;
	}

	main {
		margin: 0 auto;
		padding: 0;
	}

	footer {
		text-align: center;
		padding: 20px 0;
		font-size: 1em;
		background-color: #112240;
		color: #c0d6f7;
	}
</style>
