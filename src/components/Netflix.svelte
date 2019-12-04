<style type="text/scss">
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
  .next {
    height: 200px;
    /* background-color: #2d3e9b; */
    border-radius: 25px;
    background-image: url("./images/netflix.png");
    background-position-y: -20px;
    background-size: cover;
     &:hover {
    opacity: 0.7;
    cursor: pointer;
  }
  }
 
</style>

<main>
  <div on:click|once={gotoNetflix} class="next"></div>
</main>

<script>
let gotoNetflix = () => {
  window.open("https://netflix.com");
}
</script>
