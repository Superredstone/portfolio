<script>
	import Device from "svelte-device-info";
</script>

<main>
	<h1>Endless Runner</h1>
	{#if Device.isMobile || Device.isPhone || Device.isTablet || Device.isLegacyTouchDevice}
		<p style="margin-bottom: 600px;">
			Sorry, your device is not currently supported.
			<br />Open this page on a PC to play the game.
		</p>
	{:else}
		<iframe
			src="/portfolio/endless_runner.html"
			title="endless-runner"
			frameborder="0"
			width="1000"
			height="700"
		/>
	{/if}
</main>
