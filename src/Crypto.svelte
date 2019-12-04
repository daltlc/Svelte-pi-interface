<script>
  import { onMount } from "svelte";

  let bitcoinObj;
  let bitcoinPrice;
  let ethObj;
  let ethPrice;
  onMount(async () => {
    let bitcoinObj = await fetch(
      `https://api.cryptonator.com/api/ticker/btc-usd`
    ).then(r => r.json());
    bitcoinPrice = bitcoinObj.ticker.price;
    let ethObj = await fetch(
      `https://api.cryptonator.com/api/ticker/eth-usd`
    ).then(r => r.json());
    ethPrice = ethObj.ticker.price;

    console.log(ethObj);
    // this.r = result.data.ticker.price;
    // let price = result.data.ticker.price
    // console.log(price)
    // this.prices.push(price);
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
  .crypto_main {
    height: auto;
    background-color: #2d3e9b;
    border-radius: 25px;
    width: 400px;
    padding: 10px 20px;
    color: white;
    display: flex;
    justify-content: space-between;
  }
  h1 {
    font-family: "Montserrat", sans-serif;
    font-size: 21.4px;
  }
  h2 {
    font-size: 14px;
    font-family: "Montserrat", sans-serif;
  }
  img{
    height:100px;
    max-height:auto;
    align-self: center;
  }
</style>

<main>
  <div class="crypto_main">
    <div class="crypto_main_prices">
      <h1>Bitoin Price</h1>
      <h2>{bitcoinPrice}</h2>
      <h1>Eth Price</h1>
      <h2>{ethPrice}</h2>
    </div>
    <img src="./images/bitcoingif.gif" alt="" />

  </div>
</main>
 