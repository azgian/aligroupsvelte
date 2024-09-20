<script>
	import { onMount } from 'svelte';
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
<div style="height:400px"></div>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		font-family: Arial, sans-serif;
		background-color: #0a192f;
		color: #e6f1ff;
	}

	.container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 15px;
	}

	.hero {
		background-image: url('/images/bgp1024x1024.jpg');
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
		color: #c0d6f7;
	}

	.hero h2 {
		margin: 0;
		font-size: 2em;
		color: #eee;
	}

	.hero p {
		margin: 10px 0 20px;
	}

	button {
		background-color: #64a2ff;
		color: #0a192f;
		border: none;
		border-radius: 10px;
		padding: 15px 20px;
		font-size: 1em;
		cursor: pointer;
		transition: background-color 0.3s ease;
	}

	button:hover {
		background-color: #98bff8;
	}

	.subsidiaries {
		margin-bottom: 40px;
	}

	.subsidiaries h2 {
		text-align: center;
		color: #c0d6f7;
	}
</style>
