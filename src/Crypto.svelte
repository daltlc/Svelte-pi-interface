<script>
  import { onMount } from "svelte";
  

  onMount(async () => {
    let apiCall = await fetch(
      `https://api.cryptonator.com/api/ticker/btc-usd`
    ).then(r => r.json());
    console.log(apiCall);
        // this.r = result.data.ticker.price;
        // let price = result.data.ticker.price
        // console.log(price)
        // this.prices.push(price);
  });
</script>