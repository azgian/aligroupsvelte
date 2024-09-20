<script lang="ts">
	import Breadcrumb from '../../components/Breadcrumb.svelte';
	// Subsidiary 타입 정의
	type Subsidiary = {
		name: string;
		description: string;
		logo: string;
	};

	// 계열사 데이터
	const subsidiaries: Subsidiary[] = [
		{ name: '㈜해리코스', description: '화장품 제조 및 유통', logo: '/images/harikosu-logo.png' },
		{
			name: '㈜더해리미디어',
			description: '미디어 콘텐츠 제작',
			logo: '/images/harimedia-logo.png'
		},
		{
			name: '알리파운데이션',
			description: '비영리 자선 단체',
			logo: '/images/alifoundation-logo.png'
		},
		{ name: '홍콩해리코스', description: '해외 화장품 유통', logo: '/images/hkharikosu-logo.png' },
		{ name: '㈜알리베이', description: '전자상거래 플랫폼', logo: '/images/alibay-logo.png' },
		{
			name: '㈜플러스셀바이오',
			description: '바이오 의약품 연구 개발',
			logo: '/images/pluscellbio-logo.png'
		},
		{
			name: '중국백억유태신식자문유한공사',
			description: '중국 내 투자 자문',
			logo: '/images/chinainvest-logo.png'
		},
		{ name: '알리에프엔비', description: '식품 및 음료 제조', logo: '/images/alifnb-logo.png' }
	];

	function handleSubsidiaryClick(subsidiary: Subsidiary) {
		// 계열사 클릭 시 처리 로직
		console.log(`${subsidiary.name} 클릭됨`);
	}
</script>

<Breadcrumb path={['계열사']} />

<main class="subsidiaries">
	<section class="hero">
		<h1>ALI GROUP 계열사</h1>
		<p>혁신과 성장을 함께 이끄는 ALI GROUP의 다양한 계열사를 소개합니다.</p>
	</section>

	<section class="subsidiary-list">
		{#each subsidiaries as subsidiary}
			<div
				class="subsidiary-card"
				on:click={() => handleSubsidiaryClick(subsidiary)}
				on:keydown={(e) => e.key === 'Enter' && handleSubsidiaryClick(subsidiary)}
				tabindex="0"
				role="button"
			>
				<!-- <img src={subsidiary.logo} alt={`${subsidiary.name} 로고`} class="subsidiary-logo" /> -->
				[로고 이미지]
				<h2>{subsidiary.name}</h2>
				<p>{subsidiary.description}</p>
			</div>
		{/each}
	</section>

	<section class="group-synergy">
		<h2>그룹 시너지</h2>
		<p>ALI GROUP의 계열사들은 서로 긴밀히 협력하여 시너지를 창출하고 있습니다.</p>
		<!-- 시너지 효과를 설명하는 다이어그램이나 추가 정보를 여기에 배치 -->
	</section>
</main>

<style>
	.subsidiaries {
		max-width: 1200px;
		margin: 0 auto;
		padding: 15px;
	}

	.hero {
		text-align: center;
		padding: 4rem 0;
		background-color: #385c74;
		margin-bottom: 2rem;
	}

	.subsidiary-list {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 2rem;
	}

	.subsidiary-card {
		background-color: #607786;
		border-radius: 8px;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
		padding: 1.5rem;
		text-align: center;
		transition: transform 0.3s ease;
		cursor: pointer;
	}

	.subsidiary-card:hover {
		transform: translateY(-5px);
	}

	.subsidiary-logo {
		width: 100px;
		height: 100px;
		object-fit: contain;
		margin-bottom: 1rem;
	}

	.group-synergy {
		margin-top: 4rem;
		text-align: center;
	}

	h1,
	h2 {
		color: #112240;
	}

	/* 추가적인 스타일은 여기에 작성하세요 */
</style>
