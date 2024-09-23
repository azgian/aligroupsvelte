<script lang="ts">
	import Menu from '$lib/components/Menu.svelte';
</script>

<header>
	<div class="header-content">
		<h1>
			<a href="/">
				<img src="/images/logo256.png" alt="ALI GROUP" class="logo" />
				ALI GROUP
			</a>
		</h1>
		<Menu />
	</div>
</header>

<main>
	<slot />
</main>

<footer>
	<p>© 2023 ALI GROUP. All rights reserved.</p>
</footer>

<style>
	header {
		background: linear-gradient(135deg, #133046, #365c75);
		padding: 1rem;
		color: white;
		position: sticky;
		top: 0px;
		z-index: 100;
	}

	.header-content {
		height: 80px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		max-width: 1200px;
		margin: 0 auto;
	}

	h1 {
		margin: 0;
		font-size: 2rem;
		padding-left: 30px;
	}

	h1 a {
		display: flex;
		align-items: center;
		text-decoration: none;
		color: #fff;
	}

	.logo {
		height: 60px; /* 로고 크기를 조절하세요 */
		width: auto;
		margin-right: 15px;
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
