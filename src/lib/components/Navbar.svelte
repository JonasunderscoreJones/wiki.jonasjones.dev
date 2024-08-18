<script>
	import NavbarList from "./NavbarList.svelte";
	import { onMount } from 'svelte';
	import { afterNavigate } from '$app/navigation';
	import { recordRequest } from './analytics';

	// Function to handle navigation events
	function handleNavigation() {
		recordRequest();
	}

	// Call the analytics function on initial page load and after each navigation
	onMount(() => {
		handleNavigation();
		afterNavigate(() => {
		handleNavigation();
		});
	});

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
