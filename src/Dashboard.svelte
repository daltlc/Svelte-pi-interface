<script>
  import News from "./News.svelte";
  import Weather from "./Weather.svelte";
  import Netflix from "./Netflix.svelte";
  import Entertainment from "./Entertainment.svelte";
  import Crypto from "./Crypto.svelte";
  import Hulu from "./Hulu.svelte";

  import { fade } from "svelte/transition";

  let show = false;
  export let user;
  setTimeout(function() {
    show = true;
  }, 200);
</script>

<style>
  .dashboard__main {
    min-height: 90vh;
    display: flex;
    flex-direction: row;
  }
  ul {
    display: flex;
    justify-content: space-between;
  }
  li {
    padding: 20px 20px;
    list-style-type: none;
    cursor: pointer;
    text-align: center;
  }
  a {
    color: white;
  }
</style>

{#if show}
  <div transition:fade class="dashboard__main">
    <News />
    <div class="second">
      <Weather />
      <Netflix />
      
    </div>
    <div class="third">
      <!-- <Entertainment /> -->
      <Crypto />
      <Hulu />
    </div>

  </div>
{/if}
