<script>
	import { onMount } from 'svelte';
	import Menu from '../components/Menu.svelte';
	import SubsidiariesGrid from '../components/SubsidiariesGrid.svelte';

	let heroSection;
	let scrollY = 0;

	onMount(() => {
		const handleScroll = () => {
			scrollY = window.pageYOffset;
		};

		window.addEventListener('scroll', handleScroll);

		return () => {
			window.removeEventListener('scroll', handleScroll);
		};
	});

	$: yPos = scrollY ? scrollY / 2 : 0; // 스크롤 속도를 절반으로 줄임
</script>

<svelte:window bind:scrollY />

<main>
	<header>
		<h1>ALI GROUP</h1>
		<Menu />
	</header>

	<section class="hero" bind:this={heroSection} style="background-position: center {yPos}px;">
		<div class="hero-content">
			<h2>Welcome to ALI GROUP</h2>
			<p>A global company providing innovative business solutions</p>
			<button>Learn More</button>
		</div>
	</section>

	<section class="subsidiaries container">
		<h2>계열사</h2>
		<SubsidiariesGrid />
	</section>
	<section class="etc"></section>
	<footer class="container">
		<p>© 2023 ALI GROUP. All rights reserved.</p>
	</footer>
</main>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		font-family: Arial, sans-serif;
		background-color: #0a192f;
		color: #e6f1ff;
	}

	main {
		margin: 0 auto;
		padding: 0 20px;
	}

	.container {
		max-width: 1200px;
		margin: 0 auto;
	}

	header {
		background: #0f4c75; /* 더 진한 푸른색 헤더 */
		padding: 1rem;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
	}

	h1 {
		margin: 0;
		text-align: center;
		color: #fff;
	}

	.hero {
		background-image: url('images/bgp1024x1024.jpg');
		background-size: cover;
		background-repeat: no-repeat;
		height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		text-align: center;
		margin-bottom: 40px;
		color: #ffffff;
		position: relative;
		overflow: hidden; /* 배경 이미지가 섹션을 벗어나지 않도록 함 */
	}

	.hero-content {
		background-color: rgba(10, 25, 47, 0.7);
		padding: 2rem;
		border-radius: 10px;
		z-index: 1;
	}

	.hero h2 {
		margin: 0;
		font-size: 2.5em;
		color: #eee;
	}

	.hero p {
		margin: 10px 0 20px;
	}

	button {
		background-color: #64ffda;
		color: #0a192f;
		border: none;
		padding: 10px 20px;
		font-size: 1em;
		cursor: pointer;
		transition: background-color 0.3s ease;
	}

	button:hover {
		background-color: #45c7b3;
	}

	.subsidiaries {
		margin-bottom: 40px;
	}

	.subsidiaries h2 {
		text-align: center;
		color: #64ffda;
	}
	.etc {
		height: 500px;
	}
	footer {
		text-align: center;
		padding: 20px 0;
		font-size: 1em;
	}
</style>
