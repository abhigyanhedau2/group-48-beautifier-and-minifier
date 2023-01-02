<script>
  import { createEventDispatcher } from "svelte";
  import About from "./About.svelte";
  import Card from "./Card.svelte";
  const dispatch = createEventDispatcher();
  const changePageHandler = (language) => {
    dispatch("changePage", language);
  };
</script>

<div>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div on:click={changePageHandler.bind(null, "html")}>
    <Card>
      <img src="../assets/html.png" height="100" width="100" alt="html" />
      <label for="html">HTML</label>
    </Card>
  </div>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div on:click={changePageHandler.bind(null, "css")}>
    <Card>
      <img src="../assets/css.png" height="100" width="100" alt="css" />
      <label for="html">CSS</label>
    </Card>
  </div>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div on:click={changePageHandler.bind(null, "js")}>
    <Card>
      <img src="../assets/js.png" height="100" width="100" alt="js" />
      <label for="html">JS</label>
    </Card>
  </div>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div on:click={changePageHandler.bind(null, "json")}>
    <Card>
      <img src="../assets/json.png" height="100" width="100" alt="json" />
      <label for="html">JSON</label>
    </Card>
  </div>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div on:click={changePageHandler.bind(null, "xml")}>
    <Card>
      <img src="../assets/xml.png" height="100" width="100" alt="xml" />
      <label for="html">XML</label>
    </Card>
  </div>
  <About />
</div>

<style></style>
