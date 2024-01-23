<div id="triangle">
	<section>
		<h2>TRIANGLE</h2>
		<p>
			This is a placeholder WebGPU rendered triangle.<br />
			[display error for unsupported browsers]
		</p>
	</section>
	<canvas></canvas>
	<span>Procedure to set this up:</span>
	<ol>
		<li>Create canvas element</li>
		<li>
			intialize WebGPU: <ol>
				<li>access gpu via navigator</li>
				<li>request adapter</li>
				<li>request device</li>
			</ol>
		</li>
		<li>select canvas context</li>
		<li>configure swap chain and context</li>
		<li>create vertex and fragment shaders of triangle</li>
		<li>create render pipeline</li>
		<li>declare animation</li>
		<li>pass animation to event loop to be rendered</li>
	</ol>
</div>

<style>
	div {
		grid-column: content;
	}
	canvas {
		width: 100%;
		height: 400px;
		background-color: darkslategrey;
	}
</style>
