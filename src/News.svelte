<script>
  import Sidebar from "./components/Sidebar.svelte";
  import Footer from "./components/Footer.svelte";
  import news from "./data/news.js";
  import { onMount } from "svelte";

  onMount(() => window.scrollTo(0, 0));
</script>

<style>
  h1 {
    margin: 0px;
    font-size: 20px;
  }
</style>

<div class="pure-g" id="main-container">
  <Sidebar />
  <div id="content" class="pure-u-1 pure-u-md-3-4">
    <div id="padded-content">
      <h1>News</h1>
      <hr />
      {#each news as n}
        <div class="news-item pure-g">
          <p class="pure-u-1 pure-u-md-1-5 date">{n.date}</p>
          <p class="item pure-u-1 pure-u-md-4-5">
            {@html n.news}
          </p>
        </div>
      {/each}
    </div>
    <Footer />
  </div>
</div>
