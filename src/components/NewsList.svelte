<script>
  import { beforeUpdate } from "svelte";
  import NewsSummary from "./NewsSummary.svelte";

  const PAGE_SIZE = 20;

  export let page;

  let items;
  let offset;

  $: fetch(`https://node-hnapi.herokuapp.com/news?page=${page}`)
    .then(r => r.json())
    .then(data => {
      items = data;
      offset = PAGE_SIZE * (page - 1);
      window.scrollTo(0, 0);
    });
</script>

<style>
  a {
    padding: 2em;
    display: block;
  }

  .loading {
    opacity: 0;
    animation: 0.4s 0.8s forwards fade-in;
  }

  @keyframes fade-in {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
</style>

{#if items}
  {#each items as item, i}
    <NewsSummary {item} {i} {offset} />
  {/each}

  <!-- <a href="#/top/{page + 1}">Page {page + 1}</a> -->
{:else}
  <p class="loading">loading...</p>
{/if}
