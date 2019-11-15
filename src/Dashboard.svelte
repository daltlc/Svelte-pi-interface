<script>
  let apps = [
    {
      name: "Netflix",
      image: "",
      link: ""
    },
    {
      name: "Hulu",
      image: "",
      link: ""
    },
    {
      name: "Disney+",
      image: "",
      link: ""
    },
    {
      name: "ESPN+",
      image: "",
      link: ""
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
    {#each apps as { name, image }, i}
      <li>{name}</li>
    {/each}
  </ul>

</div>
