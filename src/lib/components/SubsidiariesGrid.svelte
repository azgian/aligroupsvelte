<script lang="ts">
	// Company 타입 정의
	type Company = {
		name: string;
		siteUrl: string;
	};

	// .grid-item 클릭시 alert창
	function handleClick(company: Company) {
		alert(`${company.name.replace('<br>', '')} 홈페이지로 이동합니다.`);
	}

	// 계열사 명단을 객체 배열로 변경
	const companies: Company[] = [
		{ name: '㈜해리코스', siteUrl: 'https://example.com' },
		{ name: '㈜더해리미디어', siteUrl: 'https://example.com' },
		{ name: '알리파운데이션', siteUrl: 'https://example.com' },
		{ name: '홍콩해리코스', siteUrl: 'https://example.com' },
		{ name: '㈜알리베이<br>(거래소)', siteUrl: 'https://example.com' },
		{ name: '㈜플러스셀바이오<br>(병원)', siteUrl: 'https://example.com' },
		{ name: '중국백억유태신식자문유한공사<br>(줄기세포영업)', siteUrl: 'https://example.com' },
		{ name: '알리에프엔비', siteUrl: 'https://example.com' }
	];
</script>

<div class="grid">
	{#each companies as company}
		<button class="grid-item" on:click={() => handleClick(company)}>
			{@html company.name}
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
		background-color: #112240;
		height: auto; /* 높이를 자동으로 조정 */
		min-height: 100px; /* 최소 높이 설정 */
		border-radius: 8px;
		display: flex; /* Flexbox 사용 */
		justify-content: center; /* 수평 중앙 정렬 */
		align-items: center; /* 수직 중앙 정렬 */
		text-align: center; /* 텍스트 중앙 정렬 (여러 줄일 경우) */
		transition: background-color 0.3s ease;
		padding: 10px; /* 내부 여백 추가 */
		box-sizing: border-box; /* 패딩을 높이에 포함 */
		font-size: 1.25rem;
		color: aliceblue;
		line-height: 1.3; /* 줄 간격 조정 */
	}

	.grid-item:hover {
		transform: translateY(-5px);
		box-shadow: 0 6px 8px rgba(0, 0, 0, 0.2);
		background-color: #3282b8; /* 밝은 푸른색 호버 효과 */
	}
</style>
