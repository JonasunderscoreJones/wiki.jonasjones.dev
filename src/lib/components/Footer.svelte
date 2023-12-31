<script>
	import "$lib/styles/style.css";
</script>

<!-- Footer.svelte -->
<footer>
	<a href="/">Home</a>
	<div class="footer">
		<p>Website by Jonas_Jones 2021 - 2024</p>
	</div>
	<nav>
		<ul>
			<li>
				<a href="https://jonasjones.dev/">Homepage</a>
			</li>
			<li>
				<a href="/about">About</a>
			</li>
			<li>
				<a href="/contact">Contact</a>
			</li>
		</ul>
	</nav>
</footer>

<style>
	footer {
		padding: 1rem;
		margin: 2rem;
		margin-bottom: 0;
		margin-top: 0;
		background: var(--container-background-color);
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
		color: inherit;
	}

	.footer {
		display: flex;
		justify-content: center;
		align-items: center;
		font-size: 20px;
	}
</style>
