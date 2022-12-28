<script>
  import Convert from "./components/Convert.svelte";
  import Footer from "./components/Footer.svelte";
  import Header from "./components/Header.svelte";
  import Home from "./components/Home.svelte";
  let activePage = "Home"; // Two pages home or convert
</script>

<Header />
<main>
  {#if activePage === "Home"}
    <Home />
  {:else}
    <Convert />
  {/if}
</main>
<Footer />

<style>
</style>
