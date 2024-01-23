<script>
	import github_icon from '$lib/assets/github-mark.svg';
	import linkedin_icon from '$lib/assets/linkedin.svg';
</script>

<ul class="links">
	<li class="github">
		<a href="https://github.com/Markfelixm" target="_blank" rel="noopener noreferrer">
			<img src={github_icon} alt="Github profile link" />
		</a>
	</li>
	<li class="linkedin">
		<a href="https://www.linkedin.com/in/markfelixmuller" target="_blank" rel="noopener noreferrer">
			<img src={linkedin_icon} alt="LinkedIn profile link" />
		</a>
	</li>
</ul>

<style>
	ul {
		list-style: none;
		box-sizing: border-box;
		margin: 0;
		padding-inline: 0;
		padding-block: 2rem;
		display: grid;
		grid-template-columns: 1fr 1fr;
		justify-items: center;
		place-content: center;
		gap: 2rem;
	}
	a {
		text-decoration: none;
		color: black;
	}
	img {
		display: block;
		max-height: 50px;
		width: auto;
	}
</style>
