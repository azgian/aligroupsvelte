<script lang="ts">
	import { page } from '$app/stores';
	import { menuItems } from '$lib';

	$: path = $page.url.pathname.split('/').filter(Boolean);
	$: breadcrumbs = [
		{ name: '홈', path: '/' },
		...path.map((segment, index) => {
			const url = '/' + path.slice(0, index + 1).join('/');
			const menuItem = menuItems.find((item) => item.path === url);
			return {
				name: menuItem ? menuItem.name : segment,
				path: url
			};
		})
	];
</script>

<nav class="breadcrumb">
	<ol>
		{#each breadcrumbs as crumb, index}
			<li>
				{#if index === breadcrumbs.length - 1}
					<span>{crumb.name}</span>
				{:else}
					<a href={crumb.path}>{crumb.name}</a>
				{/if}
			</li>
		{/each}
	</ol>
</nav>

<style>
	.breadcrumb {
		padding: 5px 0 0 15px;
		max-width: 1200px;
		margin: 0 auto;
	}

	ol {
		list-style: none;
		padding: 0;
		margin: 0;
		display: flex;
		flex-wrap: wrap;
	}

	li {
		display: flex;
		align-items: center;
	}

	li:not(:last-child)::after {
		content: '>';
		margin: 0 10px;
		color: #c5d4e2;
	}

	a {
		color: #84b9f1;
		text-decoration: none;
	}

	a:hover {
		text-decoration: underline;
	}

	span {
		color: #c5d4e2;
	}
</style>
