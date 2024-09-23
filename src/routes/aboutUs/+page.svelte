<main class="about-us">
	<section class="hero">
		<h1>ALI GROUP 소개</h1>
		<p>혁신과 성장을 추구하는 글로벌 기업</p>
		[배경 이미지]
	</section>

	<section class="company-overview">
		<h2>회사 개요</h2>
		<p>ALI GROUP은 [설립 연도]에 설립되어 [주요 사업 분야]에서 선도적인 역할을 하고 있습니다.</p>
	</section>

	<section class="vision-mission">
		<div class="vision">
			<h2>비전</h2>
			<p>[ALI GROUP의 비전 문구]</p>
		</div>
		<div class="mission">
			<h2>미션</h2>
			<p>[ALI GROUP의 미션 문구]</p>
		</div>
	</section>

	<!-- <section class="core-values">
		<h2>핵심 가치</h2>
		<ul>
			<li>혁신</li>
			<li>고객 중심</li>
			<li>지속가능성</li>
			<li>팀워크</li>
		</ul>
	</section> -->

	<section class="business-areas">
		<h2>주요 사업 영역</h2>
		<div class="business-grid">
			<!-- 각 사업 영역에 대한 카드나 설명을 여기에 추가 -->
		</div>
	</section>

	<section class="company-history">
		<h2>회사 연혁</h2>
		<!-- 타임라인 형식의 회사 연혁을 여기에 추가 -->
	</section>
</main>

<style>
	.about-us {
		max-width: 1200px;
		margin: 0 auto;
		padding: 15px;
	}

	.hero {
		text-align: center;
		padding: 4rem 0;
		background-color: #385c74;
	}

	h1,
	h2,
	h3 {
		color: #8d9da7;
	}

	section {
		margin-bottom: 3rem;
	}

	.vision-mission {
		display: flex;
		justify-content: space-between;
	}

	.vision,
	.mission {
		width: 48%;
	}

	.core-values ul {
		display: flex;
		justify-content: space-around;
		list-style-type: none;
		padding: 0;
	}

	.business-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 1rem;
	}

	/* 추가적인 스타일은 여기에 작성하세요 */
</style>
