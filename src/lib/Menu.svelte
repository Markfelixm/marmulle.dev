<script>
	import ExternalNavigation from '$lib/ExternalNavigation.svelte';
	import InternalNavigation from '$lib/InternalNavigation.svelte';
</script>

<nav>
	<InternalNavigation />
	<ExternalNavigation />
</nav>

<style>
	nav {
		grid-area: menu;
		position: sticky;
		top: 0;
		max-height: 100svh;
		display: flex;
		flex-direction: column;
		flex-wrap: nowrap;
		justify-content: flex-end;
		align-items: center;
	}
</style>
