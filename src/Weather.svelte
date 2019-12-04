<script>
  import { onMount } from "svelte";
  let name;
  let city;
  let kelvin;
  let celsius;
  let fahrenheit;
  let weatherConditions;

  onMount(async () => {
    let apiCall = await fetch(
      `https://api.openweathermap.org/data/2.5/weather?id=5809844&APPID=e319fafbf44d2f659a1fb2c13277c106`
    ).then(r => r.json());
    console.log(apiCall);
    name = apiCall.name;
    kelvin = apiCall.main.temp;
    celsius = kelvin - 273;
    fahrenheit = Math.floor(celsius * (9 / 5) + 32);
    weatherConditions = apiCall.weather[0].description.toUpperCase();
  });
</script>

<style>
  main {
    position: relative;
    max-width: 800px;
    padding: 1em;
  }

  main :global(.meta) {
    color: rgb(207, 207, 207);
    font-size: 12px;
    margin: 0 0 1em 0;
  }

  main :global(a) {
    color: rgb(255, 255, 255);
  }
  .weather_main {
    height: auto;
    background-color: #2d3e9b;
    border-radius: 25px;
    width: 400px;
    padding: 10px 20px;
    color: white;
  }
  h1{
    font-family: 'Montserrat', sans-serif;

  }
  h2 {
    font-size: 18px;
    font-family: 'Montserrat', sans-serif;

  }
</style>

<main>
  <div class="weather_main">
    <h1>{name}</h1>
    <h2>{fahrenheit}&#176</h2>
    <h2>{weatherConditions}</h2>
  </div>
</main>
