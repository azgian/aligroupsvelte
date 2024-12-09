<script lang="ts">
	type Company = {
		name: string;
		url?: string;
		logo?: string;
		logoWidth?: number;
		description?: string;
	};

	// .grid-item 클릭시 alert창
	function handleClick(company: Company) {
		if (company.url === '') {
			alert(`${company.name.replace('<br>', '')} 준비중입니다.`);
		} else {
			if (confirm(`${company.name.replace('<br>', '')} 홈페이지로 이동합니다.`)) {
				window.open(company.url, '_blank', 'noopener,noreferrer');
			}
		}
	}

	// 계열사 명단을 객체 배열로 변경
	const companies: Company[] = [
		{ name: '㈜해리코스', url: '' },
		{ name: '㈜더해리미디어', url: '' },
		{
			name: '알리파운데이션',
			url: 'https://alifoundation.io/',
			logo: 'logo_alifoundation.png',
			logoWidth: 60
		},
		{ name: '홍콩해리코스', url: '' },
		{ name: '㈜알리베이', url: '', description: '거래소' },
		{
			name: '㈜플러스셀바이오',
			url: 'https://plusscbio.com',
			logo: 'logo_plusscbio.png',
			description: '병원'
		},
		{ name: '중국백억유태신식자문유한공사', url: '', description: '줄기세포영업' },
		{ name: '알리에프엔비', url: '' }
	];
	const logoPath = '/images/';
</script>

<div class="grid">
	{#each companies as company}
		<button
			class="grid-item {company.url ? '' : 'empty-url'}"
			on:click={() => handleClick(company)}
		>
			{#if company.logo}
				<img
					src={logoPath + company.logo}
					alt={company.name}
					class="logo"
					style={company.logoWidth ? `width: ${company.logoWidth}px;` : ''}
				/>
			{/if}
			{company.name}
			{#if company.description}
				<span class="description">{company.description}</span>
			{/if}
		</button>
	{/each}
</div>

<style>
	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 20px;
	}

	.grid-item {
		background-color: #284f94;
		height: auto; /* 높이를 자동으로 조정 */
		min-height: 100px; /* 최소 높이 설정 */
		border-radius: 8px;
		display: flex; /* Flexbox 사용 */
		flex-direction: column;
		gap: 10px;
		justify-content: center; /* 수평 중앙 정렬 */
		align-items: center; /* 수직 중앙 정렬 */
		text-align: center; /* 텍스트 중앙 정�� (여러 줄일 경우) */
		transition: background-color 0.3s ease;
		padding: 10px; /* 내부 여백 추가 */
		box-sizing: border-box; /* 패딩을 높이에 포함 */
		font-size: 1.05rem;
		font-weight: 700;
		color: aliceblue;
		min-height: 150px;
	}
	.logo {
		width: 200px;
		height: auto;
		border-radius: 10px;
	}
	.description {
		font-size: 0.95rem;
		color: #6a98b6;
	}
	.grid-item:hover {
		transform: translateY(-5px);
		box-shadow: 0 6px 8px rgba(0, 0, 0, 0.2);
		background-color: #3282b8; /* 밝은 푸른색 호버 효과 */
	}
	.empty-url {
		background-color: #454c58;
	}
</style>
