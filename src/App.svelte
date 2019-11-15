<script>
	import Keypad from './Keypad.svelte';
	import Dashboard from './Dashboard.svelte'

	let pin;
	let user = {loggedIn: false};
	let currentUser;
	let currentTheme;
	$: view = pin ? pin.replace(/\d(?!$)/g, '*') : 'enter your pin';
	let users = [
		{
			username: 'Dalton',
			pin: '5555',
			icon: '',
			color:'red'
		}
	]
	const pinSubmit = () => {
		for(let i = 0;i < users.length; i++){
			if(users[i].pin === pin){
				user.loggedIn = true;
				currentUser = users[i].username;
				currentTheme = users[i].color;
			}else{
				alert('Incorrect pin, please try again.');
			}
		}
	}
</script>
<style>
h1{
	color:white;
}
</style>

{#if !user.loggedIn}
<h1 style="color: {pin ? '#333' : '#ccc'}">{view}</h1>
	<Keypad bind:value={pin} on:submit={pinSubmit}/>
{/if}
{#if user.loggedIn}
<div class = "dashboard" style="background-color: {currentTheme}">
	<h1>Welcome {currentUser} </h1>
	<Dashboard/>
</div>

{/if}
