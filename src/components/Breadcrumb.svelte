<script lang="ts">
	export let path: string[];
</script>

<nav class="breadcrumb">
	<ol>
		<li><a href="/">홈</a></li>
		{#each path as item, index}
			<li>
				{#if index === path.length - 1}
					<span>{item}</span>
				{:else}
					<a href="/{path.slice(0, index + 1).join('/')}">{item}</a>
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
