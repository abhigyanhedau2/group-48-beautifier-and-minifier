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
  <div class="container">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="card" on:click={changePageHandler.bind(null, "html")}>
      <Card>
        <img
          src="../assets/html.png"
          height="100"
          width="100"
          alt="html"
          class="html1"
        />
      </Card>
      <label for="html">HTML</label>
    </div>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div on:click={changePageHandler.bind(null, "css")}>
      <Card>
        <img
          src="../assets/css.png"
          height="100"
          width="100"
          alt="css"
          class="css1"
        />
      </Card>
      <label for="html">CSS</label>
    </div>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div on:click={changePageHandler.bind(null, "js")}>
      <Card>
        <img
          src="../assets/js.png"
          height="100"
          width="100"
          alt="js"
          class="javascript1"
        />
      </Card>
      <label for="html">JavaScript</label>
    </div>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div on:click={changePageHandler.bind(null, "json")}>
      <Card>
        <img
          src="../assets/json.png"
          height="100"
          width="100"
          alt="json"
          class="json1"
        />
      </Card>
      <label for="html">JSON</label>
    </div>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div on:click={changePageHandler.bind(null, "xml")}>
      <Card>
        <img
          src="../assets/xml2.png"
          height="100"
          width="100"
          alt="xml"
          class="xml1"
        />
      </Card>
      <label for="html">XML</label>
    </div>
  </div>
  <About />
</div>

<style>
  .container {
    margin: 80px 0px 20px;
    padding: 0rem 15rem;
    gap: 5rem;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-evenly;
  }
  @font-face {
    font-family: "Inter"; /* The name of the font */
    src: url("fonts/inter.ttf") format("truetype"); /* The location of the font file */
  }
  img {
    height: auto;
    width: 150px;
  }
  .html1 {
    margin-top: -22px;
    margin-left: -7px;
    margin-right: 4px;
    margin-bottom: 10px;
    height: 175px;
    width: 175px;
  }
  .css1 {
    margin-top: -25px;
    margin-left: -7px;
    margin-right: 4px;
    margin-bottom: 10px;
    height: 175px;
    width: 170px;
  }
  .javascript1 {
    margin-top: 25px;
    margin-left: 12px;
    margin-right: 3px;
    margin-bottom: 5px;
    height: 130px;
    width: 135px;
  }
  .json1 {
    margin-top: 25px;
    margin-left: 21px;
    margin-bottom: 22px;
    height: 120px;
    width: 120px;
  }
  .xml1 {
    margin-top: 20px;
    margin-left: 16px;
    margin-bottom: 22px;
    height: 130px;
    width: 130px;
  }
  label {
    display: flex;
    align-items: center;
    flex-direction: column;
    margin-top: 20px;
    font-weight: bold;
    font-family: "Inter", sans-serif;
  }
  @media only screen and (max-width: 1750px) {
    .container {
      padding: 0rem 5rem;
      gap: 5rem;
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: space-evenly;
    }
  }
  @media only screen and (max-width: 1450px) {
    .container {
      padding: 0rem 2rem;
      gap: 5rem;
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: space-evenly;
    }
  }
</style>
