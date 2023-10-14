<script>
	import "$lib/styles/style.css";
</script>

<!-- Footer.svelte -->
<footer class="box-shadow">
	<div class="footer-flex">
		<a href="/">Home</a>
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
	</div>
	<div class="footer">
		<p>Website by Jonas_Jones 2021 - 2023</p>
	</div>
</footer>

<style>
	footer {
		padding: 1rem;
		margin: 2rem;
		margin-bottom: 2rem;
		margin-top: 0;
		background: var(--container-background-color);
		border-radius: 0.5rem;
	}

	.footer-flex {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
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
		font-size: 20px;
		text-align: center;
	}

	@media (max-width: 550px) {
		footer {
			margin: 0;
			border-radius: 0;
		}
	}
</style>
