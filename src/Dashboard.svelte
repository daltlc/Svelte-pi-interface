<script>
  import News from "./News.svelte";
  import Weather from "./Weather.svelte";
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
  a{
      color: white;
  }
</style>

<div class="dashboard__main">
  <!-- <ul>
    {#each apps as { name, image,link }, i}
      <li> <a href="{link}">{name}</a></li>
    {/each}
  </ul> -->
  <News/>
  <Weather/>
</div>
