<script>
  import Convert from "./components/Convert.svelte";
  import Footer from "./components/Footer.svelte";
  import Header from "./components/Header.svelte";
  import Home from "./components/Home.svelte";
  let activePage = "Home"; // Two pages - home or convert
  let language = undefined; // Language - html, css, js, json, xml
  const changePageHandler = (event) => {
    activePage = activePage === "Home" ? "Convert" : "Home";
    language = event.detail;
  };
</script>

<main>
  {#if activePage === "Home"}
    <Header heading="Beautify and Minify Tools" />
    <Home on:changePage={changePageHandler} />
  {:else}
    <Header
      hasHomeBtn
      heading={`${language.toUpperCase()} Beautifier and Minifier`}
      on:changePage={changePageHandler}
    />
    <Convert {language} />
  {/if}
</main>
<Footer />

<style>
</style>
