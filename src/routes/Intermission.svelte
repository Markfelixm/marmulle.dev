<slot>
	<div></div>
</slot>

<style>
	div {
		grid-column: full-width;
		background-color: darkslategrey;
		background-image: url($lib/assets/busy_space.webp);
		background-size: cover;
		padding-block: 15svh;
		width: 100%;
		min-height: 15svh;
		max-height: 45svh;
		animation-timeline: view();
		animation-name: shift-background;
		animation-fill-mode: both;
		animation-duration: 1ms;
		animation-timing-function: linear;
	}
	@keyframes shift-background {
		from {
			background-position-y: 500px;
		}
		to {
			background-position-y: 1000px;
		}
	}
</style>
