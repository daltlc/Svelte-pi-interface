<script>
  import { onMount } from "svelte";

  import NewsList from "./NewsList.svelte";

  import NewsItems from "./NewsItems.svelte";

  let item;
  let page;

  async function hashchange() {
    // the poor man's router!
    const path = window.location.hash.slice(1);

    if (path.startsWith("/item")) {
      const id = path.slice(6);
      item = await fetch(`https://node-hnapi.herokuapp.com/item/${id}`).then(
        r => r.json()
      );

      window.scrollTo(0, 0);
    } else if (path.startsWith("/top")) {
      page = +path.slice(5);
      item = null;
    } else {
      window.location.hash = "/top/1";
    }
  }

  onMount(hashchange);
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

  .news-container {
    overflow-y: scroll;
    height: 80vh;
    background-color: rgb(24, 24, 24);
    padding: 10px 20px;
    width:500px;
  }
</style>

<svelte:window on:hashchange={hashchange} />

<main>
  <div class="news-container">
    {#if item}
      <NewsItems {item} returnTo="#/top/{page}" />
    {:else if page}
      <NewsList {page} />
    {/if}
  </div>
</main>
