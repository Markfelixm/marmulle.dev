<div class="wrapper">
	<section id="welcome">
		<div class="gold"></div>
		<div class="pink"></div>
		<h1>hi, i'm marmulle</h1>
		<span>low-level, machine learning, graphics, <span class="blinking">|</span> </span>
	</section>
</div>

<style>
	.wrapper {
		grid-column: full-width;
		background-color: darkslategrey;
		background-image: url($lib/assets/asteroids.webp);
		background-size: cover;
		padding-block: 15svh;
		width: 100%;
		height: auto;
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
	section {
		grid-column: content;
		background-color: aquamarine;
		position: relative;
	}
	.gold,
	.pink {
		height: 100%;
		position: absolute;
		right: 0;
		width: 21%;
		background-color: var(--brilliant-gold);
	}
	.pink {
		width: 7%;
		background-color: pink;
	}
	h1 {
		grid-column: content;
		color: whitesmoke;
		font-size: 3em;
		-webkit-text-stroke: 0.1rem darkslategrey;
		text-shadow:
			3px 3px 0 pink,
			5px 5px 0 var(--brilliant-gold),
			7px 7px 0 darkslategrey;
	}
	span {
		padding-inline-start: 2rem;
	}
	.blinking {
		padding-inline-start: 0;
		animation: 1s blink ease infinite;
	}
	@keyframes blink {
		from,
		to {
			color: transparent;
		}
		50% {
			color: black;
		}
	}
</style>
