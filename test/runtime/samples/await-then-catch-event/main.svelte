<script>
	export let button;
	export let thePromise;
	export let clicked;
</script>

{#await thePromise}
	<p>loading...</p>
{:then theValue}
	<button bind:this={button} on:click='{() => clicked = theValue}'>click me</button>
{:catch theError}
	<p>oh no! {theError.message}</p>
{/await}