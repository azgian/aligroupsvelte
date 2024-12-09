<script lang="ts">
	type Company = {
		name: string;
		url?: string;
		logo?: string;
		logoWidth?: number;
		description?: string;
	};

	function handleClick(company: Company) {
		if (company.url === '') {
			alert(`${company.name} 준비중입니다.`);
		} else {
			if (confirm(`${company.name} 홈페이지로 이동합니다.`)) {
				window.open(company.url, '_blank', 'noopener,noreferrer');
			}
		}
	}

	const companies: Company[] = [
		{ name: '㈜해리코스', url: '' },
		{ name: '㈜더해리미디어', url: '' },
		{
			name: '알리파운데이션',
			url: 'https://alifoundation.io/',
			logo: 'logo256.png',
			logoWidth: 60
		},
		{ name: '홍콩해리코스', url: '' },
		{
			name: '㈜알리베이',
			url: 'https://alibae.io/',
			description: '거래소',
			logo: 'logo_alibae.png',
			logoWidth: 150
		},
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
		height: auto;
		min-height: 150px;
		border-radius: 8px;
		display: flex;
		flex-direction: column;
		gap: 10px;
		justify-content: center;
		align-items: center;
		text-align: center;
		transition: background-color 0.3s ease;
		padding: 10px;
		box-sizing: border-box;
		font-size: 1.05rem;
		font-weight: 700;
		color: aliceblue;
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
		background-color: #3282b8;
	}
	.empty-url {
		background-color: #454c58;
	}
</style>
