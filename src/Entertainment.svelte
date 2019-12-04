<script>
let name = 'Demo';
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
  .ent_main {
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
  <div class="ent_main">
    <h1>{name}</h1>
   <h2>{name}</h2>
   <h2>{name}</h2>
  </div>
</main>