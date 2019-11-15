<script>
  let apps = [
    {
      name: "Netflix",
      image: "",
      link: "https://www.netflix.com"
    },
    {
      name: "Hulu",
      image: "",
      link: "https://www.hulu.com"
    },
    {
      name: "Disney+",
      image: "",
      link: "https://www.disneyplus.com"
    },
    {
      name: "ESPN+",
      image: "",
      link: "https://plus.espn.com"
    }
  ];
</script>

<style>
  .dashboard__main {
  }
  ul {
    display: flex;
    justify-content: space-between;
  }
  li {
    padding: 20px 40px;
    list-style-type: none;
    color: white;
    cursor: pointer;
  }
</style>

<div class="dashboard__main">
  <ul>
    {#each apps as { name, image,link }, i}
      <li> <a href="{link}">{name}</a></li>
    {/each}
  </ul>

</div>
