<script>
  import axios from "axios";
 let items;
  const getNews = () => {
//     let stories = [];
//     let err = "";
//     console.log("hello");
//     axios
//       .get("https://hacker-news.firebaseio.com/v0/topstories.json")
//       .then(result => {
//         this.results = result.data.slice(0, 15);
//         this.results.forEach(element => {
//             console.log(this.results)
//           axios
//             .get(
//               "https://hacker-news.firebaseio.com/v0/item/" + element + ".json"
//             )
//             .then(result => {
//               this.stories.push(result);
//             })
//             .catch(err => {
//               console.log(err);
//             });
//         });
//       })
//       .catch(err => {
//         err = err;
//       });
//   }; 
    $: fetch(`ttps://hacker-news.firebaseio.com/v0/topstories.json`)
    .then(r => r.json())
		.then(data => {
            items = data;
        });



  }
  getNews();
</script>


{#if items}
	{#each items as item, i}
		<li>{item} {i} </li>
	{/each}

{:else}
	<p class="loading">loading...</p>
{/if}