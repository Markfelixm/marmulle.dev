<script>
	import Menu from '$lib/Menu.svelte';
	import Welcome from './Welcome.svelte';
	import About from './About.svelte';
	import SchibstedConnect from './SchibstedConnect.svelte';
	import Intermission from './Intermission.svelte';
	import Hive from './Hive.svelte';
	import Triangle from './Triangle.svelte';

	import Filler from './filler.svelte'; // TODO: rm
</script>

<div class="view">
	<Menu />
	<main class="content-grid">
		<section class="full-width" id="top">
			<a href="#bottom">to bottom</a>
		</section>
		<Welcome />
		<About />
		<p>/ WORK IN PROGRESS /</p>
		<SchibstedConnect />
		<Intermission />
		<Hive />
		<Filler />
		<Triangle />
		<Filler />
		<section class="full-width" id="bottom">
			<a href="#top">to top</a>
		</section>
	</main>
</div>

<style>
	.view {
		display: grid;
		grid-template: 'menu main';
		grid-template-columns: 1fr 4fr;
		justify-items: stretch;
	}
	.content-grid {
		grid-area: main;
		display: grid;
		grid-template-columns: [full-width-start] 1fr [breakout-start] 1fr [content-start] 4fr [content-end] 1fr [breakout-end] 1fr [full-width-end];
	}
	.content-grid > * {
		grid-column: content;
	}
	.content-grid > .full-width {
		grid-column: full-width;
	}
	a {
		color: black;
	}
	/* color palette:
		whitesmoke
		pink
		aquamarine
		(gold) #FFE175
		darkslategrey
		black */
</style>
