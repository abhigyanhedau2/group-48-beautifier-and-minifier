<script>
  import Button from "./Button.svelte";
  export let language = undefined;
  let inputText = "";
  let outputText = "";
  const htmlBeautifier = () => {
    console.log("beatify html");
  };
  const cssBeautifier = () => {
    console.log("beatify css");
  };
  const jsBeautifier = () => {
    console.log("beatify js");
  };
  const jsonBeautifier = () => {
    console.log("beatify json");
    outputText = JSON.stringify(JSON.parse(inputText), null, 2);
  };
  const xmlBeautifier = () => {
    console.log("beatify xml");
    var formatted = "";
    var indent = "";
    var tab = "\t";
    inputText.split(/>\s*</).forEach(function (node) {
      if (node.match(/^\/\w/)) indent = indent.substring(tab.length); // decrease indent by one 'tab'
      formatted += indent + "<" + node + ">\r\n";
      if (node.match(/^<?\w[^>]*[^\/]$/)) indent += tab; // increase indent
    });
    outputText = formatted.substring(1, formatted.length - 3);
  };
  const beautifier = () => {
    switch (language) {
      case "html":
        htmlBeautifier();
        break;
      case "css":
        cssBeautifier();
        break;
      case "js":
        jsBeautifier();
        break;
      case "json":
        jsonBeautifier();
        break;
      case "xml":
        xmlBeautifier();
        break;
      default:
        break;
    }
  };
  const minifier = () => {
    console.log("minify " + language);
    outputText = inputText.replace(/\s+/g, "");
  };
  const htmlMinifier = () => {
    console.log("minify html");
  };
  const clearInputTextBox = () => {
    console.log("clear input text box");
    inputText = "";
    outputText = "";
  };
</script>

<div class="container">
  <p>Enter your {language.toUpperCase()} code:</p>
  <div>
    <i class="fa-regular fa-clipboard" />
    <textarea bind:value={inputText} rows={5} cols={50} />
  </div>
</div>
<div class="btnGroup">
  <Button on:clickEvent={beautifier.bind(null, language)}>Beautify</Button>
  <Button on:clickEvent={minifier}>Minify</Button>
  <Button on:clickEvent={clearInputTextBox}>Clear</Button>
</div>
<div class="container">
  <p>Beautified HTML code:</p>
  <div>
    <i class="fa-regular fa-clipboard" />
    <textarea readonly bind:value={outputText} rows={5} cols={50} />
  </div>
</div>

<style></style>
