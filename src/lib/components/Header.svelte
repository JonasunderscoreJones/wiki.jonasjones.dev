<!-- Header.svelte -->
<body style="background-color: {$isDarkMode ? '#fff' : '#16181c'};padding:0">
	<header>
		<div class="header-title">
			<a href="/"><img src="/favicon.png" alt="logo" width="50" height="50"><h1 style="">wiki.jonasjones.dev</h1></a>
		</div>
		<nav>
			<ul>
				<li>
					<a href="/about">About</a>
				</li>
				<li>
					<a href="/contact">Contact</a>
				</li>
				<li>
					<DarkModeSwitcher />
				</li>
			</ul>
		</nav>
	</header>
</body>

<style>
	header {
		padding: 1rem;
		margin: 2rem;
		margin-top: 0;
		margin-bottom: 0;
		background: rgb(0, 255, 0);
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		border-radius: 0.5rem;
	}

	ul {
		margin: 0;
		list-style-type: none;
		display: flex;
		gap: 1rem;
	}

	a {
		text-decoration: none;
		color: black;
	}

	a:hover {
		color: #26292f;
	}

	h1 {
		font-size:35px;
		padding:0;
		margin:0;
		margin-left:20px;
		float: left;
	}

	img {
		float: left;
	}
	.header-title {
		display: flex;
		align-items: center;
		float: left;
		clear: both;
	}

	button#dark-mode-toggle {
    background-color: transparent;
    border: none;
    cursor: pointer;
	}

	button#dark-mode-toggle img {
		width: 30px;
		height: 30px;
	}
</style>
<script>
	import DarkModeSwitcher from '$lib/components/DarkModeSwitcher.svelte';
	import { isDarkMode } from '$lib/stores/darkModeStore.js';

	function toggleDarkMode() {
	$isDarkMode = !$isDarkMode;
	document.body.classList.toggle("dark-mode", $isDarkMode);
	}

</script>