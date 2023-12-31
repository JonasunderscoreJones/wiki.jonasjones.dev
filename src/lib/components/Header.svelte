<!-- Header.svelte -->
<header>
	<div class="header-title">
		<a href="/"
			><img src="/favicon.png" alt="logo" width="50" height="50" />
			<h1 style="">Jonas_Jones Wiki</h1></a
		>
	</div>
	<nav>
		<ul>
			<li>
				<a href="https://jonasjones.dev/"
					><img
						style="padding-top: 7px;"
						src="/homepage.png"
						height="30px"
						alt="Homepage"
					/></a
				>
			</li>
		</ul>
	</nav>
</header>

<style>
	header {
		padding: 1rem;
		margin: 2rem;
		margin-top: 2rem;
		margin-bottom: 0;
		background: rgb(0, 255, 0);
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		border-radius: 0.5rem;
		box-shadow: 2px 2px rgb(0, 180, 0);
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
		font-size: 35px;
		padding: 0;
		margin: 0;
		margin-left: 20px;
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

	@media screen and (max-width: 550px) {
		header h1 {
			font-size: 20px;
			float:none;
			padding-left: 40px;
		}

		header {
			margin: 0;
			border-radius: 0;
			text-align: left;
		}
	}
</style>
