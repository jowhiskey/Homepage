<script>
	import Navbar from '$lib/Navbar.svelte';
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href="/static/Logo-short.svg" />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<Navbar></Navbar>

{@render children()}

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		font-family: 'Inter', system-ui, -apple-system, sans-serif;
		background: #ffffff;
		overflow-x: hidden;
	}

	:global(*) {
		box-sizing: border-box;
	}
</style>
