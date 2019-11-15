<script>
	import Keypad from './Keypad.svelte';

	let pin;
	let user = {loggedIn: false};
	$: view = pin ? pin.replace(/\d(?!$)/g, '*') : 'enter your pin';

	const handleSubmit = () => {
		if(pin === '5555'){
			user.loggedIn = true;
		}
	}
</script>
<style>

</style>

{#if !user.loggedIn}
<h1 style="color: {pin ? '#333' : '#ccc'}">{view}</h1>
	<Keypad bind:value={pin} on:submit={handleSubmit}/>
{/if}
{#if user.loggedIn}
<h1>Welcome</h1>
{/if}
