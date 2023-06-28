<script lang="ts">
	import {
		IconBrandDiscord,
		IconBrandGithub,
		IconBrandTwitter,
		IconLoader,
	} from "@tabler/icons-svelte";

	let sendingEmail = false;

	async function handleSubmit(data: SubmitEvent) {
		sendingEmail = true;

		const formData = new FormData(data.currentTarget as HTMLFormElement);
		const object = Object.fromEntries(formData);
		const json = JSON.stringify(object);

		const response = await fetch("https://api.web3forms.com/submit", {
			method: "POST",
			headers: {
				"Content-Type": "application/json",
				Accept: "application/json",
			},
			body: json,
		});

		const result = await response.json();

		sendingEmail = false;

		if (result.success) {
			console.log(result);

			alert("Message sent! Thank you!");
		} else {
			alert("Error: Unable to send email, try again later :/");
		}
	}
</script>

<main>
	<div class="social-medias">
		<h1>Social media</h1>
		<span
			><IconBrandDiscord />
			<p>Discord:</p>
			<a
				target="_blank"
				href={"https://discordapp.com/users/294164191437127702"}>@kcirtap69</a
			></span
		>
		<span>
			<IconBrandTwitter />
			<p>Twitter:</p>
			<a target="_blank" href="https://twitter.com/superredstone19"
				>@superredstone19</a
			>
		</span>
		<span>
			<IconBrandGithub />
			<p>Github:</p>
			<a target="_blank" href="https://github.com/Superredstone"
				>@SuperRedstone</a
			>
		</span>
	</div>

	<h1>Send me a message</h1>
	{#if sendingEmail}
		<div class="loader"><IconLoader height="24" width="24" /></div>
	{:else}
		<form on:submit|preventDefault={handleSubmit}>
			<input
				type="hidden"
				name="access_key"
				value="f39851db-ec51-4568-8ed4-bd0212b9feaa"
			/>
			<input type="text" name="name" required placeholder="Name" />
			<input type="email" name="email" required placeholder="Email" />
			<textarea name="message" rows="3" placeholder="Message" />
			<button type="submit" value="">Submit</button>
		</form>
	{/if}
</main>

<style>
	span {
		display: flex;
		flex-direction: row;
		width: fit-content;
		align-items: center;
	}

	span > a {
		margin-left: 10px;
	}

	span > p {
		margin-left: 15px;
		margin-top: 3px;
		margin-bottom: 3px;
	}

	main {
		display: flex;
		flex-direction: column;
		justify-content: center;
		font-size: 1.5rem;
	}

	form {
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
		gap: 20px;
		width: 45%;
	}

	input {
		border-radius: 5px;
		border-width: 0;
		height: 1.7rem;
		padding: 15px;
		font-size: larger;
	}

	@media (max-width: 1200px) {
		form {
			width: 100%;
		}
	}

	@media (max-width: 600px) {
		button {
			width: max-content;
		}
	}

	textarea {
		font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
		font-size: larger;
		padding: 3px 7px;
		resize: none;
		outline: none;
		border: none;
		border-radius: 5px;
	}

	input:focus,
	textarea:focus {
		outline: none;
	}

	button {
		padding: 8px;
		width: 50%;
		background-image: linear-gradient(100deg, var(--primary), var(--accent));
		border: none;
		color: var(--text);
		font-weight: bold;
		border-radius: 15px;
		transition: transform 0.2;
		font-size: larger;
	}

	button:hover {
		transform: scale(105%);
		cursor: pointer;
	}

	a {
		text-decoration: none;
		color: var(--primary);
		transition: color 0.25s;
	}

	a:hover {
		color: var(--accent);
	}

	.loader {
		width: 24px;
		height: 24px;
		animation: spin 2s infinite linear;
	}

	@keyframes spin {
		0% {
			transform: rotate(0deg);
		}

		100% {
			transform: rotate(360deg);
		}
	}
</style>
