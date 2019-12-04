<script>
  export let item;
  export let returnTo;
</script>

<style>
  article {
    margin: 0 0 1em 0;
  }

  a {
    display: block;
    margin: 0 0 1em 0;
  }

  h1 {
    font-size: 1.4em;
    margin: 0;
    font-family: "Montserrat", sans-serif !important;
  }
</style>

<a href={returnTo}>&laquo; back</a>

<article>
  <a href={item.url}>
    <h1>{item.title}</h1>
    <small>{item.domain}</small>
  </a>

  <p class="meta">submitted by {item.user} {item.time_ago}</p>
</article>
