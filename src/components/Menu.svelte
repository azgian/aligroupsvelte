<script lang="ts">
	let isMenuOpen = false;

	function toggleMenu() {
		isMenuOpen = !isMenuOpen;
	}
</script>

<nav>
	<button class="menu-icon" on:click={toggleMenu} aria-label="메뉴 열기">
		<span class:open={isMenuOpen}></span>
		<span class:open={isMenuOpen}></span>
		<span class:open={isMenuOpen}></span>
	</button>
	<ul class:open={isMenuOpen}>
		<li><a href="/" on:click={toggleMenu}>홈</a></li>
		<li><a href="/aboutUs" on:click={toggleMenu}>회사 소개</a></li>
		<li><a href="/subsidiaries" on:click={toggleMenu}>계열사</a></li>
	</ul>
</nav>

<style>
	nav {
		position: relative;
		height: 100%;
		width: 50%;
	}

	.menu-icon {
		display: none;
		flex-direction: column;
		justify-content: space-around;
		width: 2rem;
		height: 2rem;
		background: transparent;
		border: none;
		cursor: pointer;
		padding: 0;
		z-index: 10;
	}

	.menu-icon span {
		width: 2rem;
		height: 0.25rem;
		background: #fff;
		border-radius: 10px;
		transition: all 0.3s linear;
		position: relative;
		transform-origin: 1px;
	}

	.menu-icon span:first-child {
		transform: rotate(0);
	}

	.menu-icon span:nth-child(2) {
		opacity: 1;
		transform: translateX(0);
	}

	.menu-icon span:nth-child(3) {
		transform: rotate(0);
	}

	.menu-icon span.open:first-child {
		transform: rotate(45deg);
	}

	.menu-icon span.open:nth-child(2) {
		opacity: 0;
		transform: translateX(20px);
	}

	.menu-icon span.open:nth-child(3) {
		transform: rotate(-45deg);
	}

	ul {
		position: absolute;
		bottom: 0px;
		right: 10px;
		display: flex;
		list-style-type: none;
		padding: 0;
		margin: 0;
	}

	li a {
		color: #fff;
		text-decoration: none;
		padding: 5px 15px;
		border-radius: 5px;
		font-size: 1.25rem;
	}

	a:hover {
		background: rgba(255, 255, 255, 0.3); /*#0a192f*/
	}

	@media (max-width: 768px) {
		nav {
			position: static; /* relative에서 static으로 변경 */
			width: auto; /* 50%에서 auto로 변경 */
		}

		.menu-icon {
			display: flex;
			position: absolute;
			right: 25px;
			bottom: 15px;
		}

		ul {
			flex-direction: column;
			position: fixed; /* absolute에서 fixed로 변경 */
			top: 0; /* 95px에서 0으로 변경 */
			right: 0; /* -20px에서 0으로 변경 */
			bottom: 0; /* 새로 추가 */
			transform: translateX(100%);
			transition: transform 0.3s ease-in-out;
			background: #0f4c75;
			width: 200px;
			padding: 115px 0 0; /* 상단 패딩 추가 */
			margin: 0;
			box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
			overflow-y: auto; /* 세로 스크롤 추가 */
		}

		ul.open {
			transform: translateX(0);
		}

		li {
			margin: 0;
			padding: 0;
			background: #0f4c75;
			border-bottom: 1px solid rgba(255, 255, 255, 0.3);
		}

		li:last-child {
			border-bottom: none;
		}

		li a {
			display: block;
			text-align: center;
			padding: 12px 10px;
			transition: background-color 0.3s ease;
			border-radius: 0px;
		}

		li a:hover {
			background-color: rgba(255, 255, 255, 0.3);
			text-decoration: none;
		}
	}
</style>
