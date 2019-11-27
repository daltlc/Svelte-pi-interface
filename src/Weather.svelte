<script>
	import { onMount } from 'svelte';

onMount(async () => {
 let apiCall = await fetch(`https://api.openweathermap.org/data/2.5/forecast?id=5809844&APPID=e319fafbf44d2f659a1fb2c13277c106`)
		.then(r => r.json())
        console.log(apiCall);
});
         
</script>
<style>
  .weather_main {
    height: 40vh;
    background-color: red;
  }
</style>

<main>
  <div class="weather_main">
  <!-- <h1>{city},{state}</h1>
  <li>{temp}</li> -->
  </div>
</main>


