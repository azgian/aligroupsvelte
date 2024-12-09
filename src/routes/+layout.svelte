<script lang="ts">
	import { page } from '$app/stores';
	import Menu from '$lib/components/Menu.svelte';
	import Nav from '$lib/components/Nav.svelte';
	import { goto } from '$app/navigation';
	$: isHome = $page.url.pathname === '/';
</script>

<header>
	<div class="header-content">
		<!-- svelte-ignore a11y_click_events_have_key_events -->
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<div class="logo-container" on:click={() => goto('/')}>
			<img src="/images/logo256.png" alt="ALI GROUP" class="logo" />
			<img src="/images/text_aligroup300.png" alt="ALI Group" class="logo-text" />
		</div>
		<!-- <Menu /> -->
	</div>
</header>

{#if !isHome}
	<Nav />
{/if}

<main>
	<slot />
</main>

<footer>
	<p>© 2023 ALI GROUP. All rights reserved.</p>
	<p><a href="mailto:algc@algc.io">algc@algc.io</a></p>
</footer>

<style>
	header {
		background: linear-gradient(135deg, #133046, #4c6e85);
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

	.logo-container {
		display: flex;
		align-items: center;
		cursor: pointer;
		gap: 10px;
	}

	.logo {
		height: 65px; /* 로고 크기를 조절하세요 */
		width: auto;
	}
	.logo-text {
		height: 55px;
		width: auto;
	}

	@media (max-width: 768px) {
		.header-content {
			height: 50px;
		}
		.logo {
			height: 45px; /* 로고 크기를 조절하세요 */
			width: auto;
		}
		.logo-text {
			height: 35px;
			width: auto;
		}
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
		height: 150px;
	}
	footer a {
		color: #c0d6f7;
		text-decoration: none;
		border: solid 1px #c0d6f7;
		padding: 5px;
		border-radius: 5px;
	}
</style>
