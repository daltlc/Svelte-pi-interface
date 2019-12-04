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
  .hulu_main {
    height: 200px;
    /* background-color: #2d3e9b; */
    border-radius: 25px;
    background-image: url("./images/hulu.jpg");
    background-position-y: -20px;
    background-size: cover;
  }
  .hulu_main:hover {
    opacity: 0.7;
    cursor: pointer;
  }
</style>

<main>
  <div on:click|once={gotoHulu} class="hulu_main"></div>
</main>

<script>
let gotoHulu = () => {
  window.open("https://hulu.com");
}
</script>
