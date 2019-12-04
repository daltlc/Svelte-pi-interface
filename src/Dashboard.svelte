<script>
  import News from "./News.svelte";
  import Weather from "./Weather.svelte";
  import Next from "./Next.svelte";
  import Entertainment from "./Entertainment.svelte";
  import Crypto from "./Crypto.svelte";
  import { fade } from 'svelte/transition';


  let show = false;
  export let user;

  // let apps = [
  //   {
  //     name: "Netflix",
  //     image: "",
  //     link: "https://www.netflix.com"
  //   },
  //   {
  //     name: "Hulu",
  //     image: "",
  //     link: "https://www.hulu.com"
  //   },
  //   {
  //     name: "Disney+",
  //     image: "",
  //     link: "https://www.disneyplus.com"
  //   },
  //   {
  //     name: "ESPN+",
  //     image: "",
  //     link: "https://plus.espn.com"
  //   }
  // ];
 setTimeout(function(){ show = true }, 200);

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
  {#if user === 'Dalton'}
    <News />
    <div class="second">
      <Weather />
      <Next />
      <Next />
    </div>
    <div class="third">
      <Entertainment />
      <Crypto />
      <Next />
    </div>
  {/if}
  {#if user === 'Carissa'}{/if}
  <!-- <ul>
    {#each apps as { name, image,link }, i}
      <li> <a href="{link}">{name}</a></li>
    {/each}
  </ul> -->

</div>
{/if}
