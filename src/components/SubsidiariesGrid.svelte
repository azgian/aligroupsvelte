<div class="grid">
	<div class="grid-item">(주)해리코스</div>
	<div class="grid-item">홍콩해리코스</div>
	<div class="grid-item">알리파운데이션</div>
	<div class="grid-item">(주)더해리미디어</div>
	<div class="grid-item">(주)알리베이(거래소)</div>
	<div class="grid-item">(주)플러스셀바이오(병원)</div>
	<div class="grid-item">중국백억유태신식자문유한공사<br />(줌기세포 영업)</div>
	<div class="grid-item">알리에프엔비</div>
</div>

<style>
	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 20px;
	}

	.grid-item {
		background-color: #112240;
		height: 100px; /* 높이를 80px로 설정 */
		border-radius: 8px;
		display: flex; /* Flexbox 사용 */
		justify-content: center; /* 수평 중앙 정렬 */
		align-items: center; /* 수직 중앙 정렬 */
		text-align: center; /* 텍스트 중앙 정렬 (여러 줄일 경우) */
		transition: background-color 0.3s ease;
		padding: 10px; /* 내부 여백 추가 */
		box-sizing: border-box; /* 패딩을 높이에 포함 */
		font-size: 1.25rem;
	}

	.grid-item:hover {
		transform: translateY(-10px);
		box-shadow: 0 6px 8px rgba(0, 0, 0, 0.2);
		background-color: #3282b8; /* 밝은 푸른색 호버 효과 */
	}
</style>
