<script>
	import NavbarList from "./NavbarList.svelte";

	let searchterm = "";

</script>

<div class="container navbar">
	<div class="row">
		<input class="box-shadow-inverted" type="text" bind:value={searchterm} placeholder="Search Pages (Alpha)..." />
		<div class="col-md-12">
			<h2>Pages</h2>
			<div class="navbar-links">
				<NavbarList {searchterm} />
			</div>
		</div>
	</div>
</div>
