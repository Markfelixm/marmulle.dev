<script>
	import successful_message_image from '$lib/assets/radio.webp';
	import { onMount } from 'svelte';

	let sent = false;
	let success = false;
	onMount(() => {
		const form = document.getElementById('contact-form');

		form.addEventListener('submit', function (event) {
			event.preventDefault();

			fetch('https://usebasin.com/f/749f07577fc2', {
				method: 'POST',
				body: new FormData(form)
			})
				.then((response) => {
					if (response.ok) {
						sent = true;
						success = true;
					} else {
						sent = true;
						success = false;
					}
				})
				// TODO: send an error report and notify user what went wrong
				.catch((error) => {
					console.error('Error:', error);
				});
		});
	});
</script>

<section id="contact">
	<h1>CONTACT</h1>

	{#if !sent}
		<span>Feel free to get in touch! <em>Your details will not be distributed.</em></span>
		<!-- TODO: check validity -->
		<form id="contact-form">
			<input type="text" name="name" placeholder="Name" class="name" required maxlength="64" />
			<input
				type="email"
				name="email"
				placeholder="Email"
				class="email"
				inputmode="email"
				required
				maxlength="64"
			/>
			<textarea
				type="text"
				name="message"
				placeholder="Message (up to 512 characters)"
				class="message"
				required
				maxlength="512"
				cols="30"
				rows="10"
			></textarea>
			<button type="submit" class="submit">Send</button>
		</form>
	{:else if success}
		<div class="success">
			<span>//// [TRANSMISSION RECEIVED] //// [THANK YOU] ////</span>
			<img
				src={successful_message_image}
				alt="a futuristic sci-fi radio letting you know your message was sent successfully"
			/>
		</div>
	{:else}
		<a href="https://www.linkedin.com/in/markfelixmuller" target="_blank" rel="noopener noreferrer">
			//// [TRANSMISSION FAILED] //// [REASON UNKNOWN] //// [REDIRECT TRANSMISSION] //// [ENTER
			LINKEDIN] //// [EXPLETIVES AUTHORIZED] ////
		</a>
	{/if}
</section>

<style>
	section {
		grid-column: content;
		background-color: aquamarine;
	}
	span {
		padding-inline-start: 1rem;
	}
	form {
		margin: 1rem;
		padding-inline-end: 1rem;
		display: grid;
		grid-template-areas:
			'name email email'
			'message message message'
			'submit submit submit';
	}
	form > * {
		margin: 0.5rem;
		padding: 0.5rem;
		border: 0.125rem black solid;
	}
	.name {
		grid-area: name;
	}
	.email {
		grid-area: email;
	}
	.message {
		grid-area: message;
	}
	.submit {
		grid-area: submit;
	}
	.success {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	img {
		max-width: 320px;
		margin: 2em;
	}
</style>
