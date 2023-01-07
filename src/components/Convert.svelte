<script>
  import Button from "./Button.svelte";
  import js_beautify from "js-beautify";
  import cssbeautify from "cssbeautify";

  export let language = undefined;
  let inputText = "";
  let outputText = "";

  const htmlBeautifier = () => {
    console.log("beatify html");
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

  const cssBeautifier = () => {
    console.log("beatify css");
    outputText = cssbeautify(inputText, { autosemicolon: true });
  };

  const jsBeautifier = () => {
    console.log("beatify js");
    outputText = js_beautify(inputText, { indent_size: 2 });
  };

  const jsonBeautifier = () => {
    console.log("beatify json");
    outputText = JSON.stringify(JSON.parse(inputText), null, 2);
  };

  const xmlBeautifier = () => {
    console.log("beatify xml");
    htmlBeautifier();
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

  const clearInputTextBox = () => {
    console.log("clear input text box");
    inputText = "";
    outputText = "";
  };

  const pasteInput = async () => {
    inputText = await navigator.clipboard.readText();
  };

  const copyOutput = async () => {
    navigator.clipboard.writeText(outputText);
  };
</script>

<body>
<div id="d1">
  <div class="container box">
    
  <div class="container box">
    <p>Enter your that code:</p>
    <div>
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <i on:click={pasteInput} class="fa-regular fa-clipboard fa-lg" />
      <textarea bind:value={inputText} rows={5} cols={50} ></textarea>
    </div>
  </div>
  <div class="btnGroup box">
    <Button on:clickEvent={beautifier.bind(null, language)}>Beautify</Button>
    <Button on:clickEvent={minifier}>Minify</Button>
    <Button on:clickEvent={clearInputTextBox} type="secondary">Clear</Button>
  </div>
  
  <div class="container box">
    <p>Output code:</p>
    <div>
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <i on:click={copyOutput} class="fa-regular fa-copy fa-lg" />
      <textarea readonly bind:value={outputText} rows={5} cols={50} />
    </div>
  </div>
  
</div>
</div>
</body>
<style>
  body{
    font-family: 'Inter',sans-serif;
    
  }
  #d1{
   display: flex;
   flex-wrap: wrap;
    width: 100%;
    margin-right: 0;
    justify-content: center;
  }
  .container{
   justify-content: center;
  }
  .btnGroup {
    display: flex;
    flex-direction: column;
    margin-bottom: 0px;
    justify-content: center;
    align-items: center;
    margin-top: 15%;
}
  textarea{
    background-color: #f6f6f6;
    border-radius: 8px;
    resize: none;
    height: 450px;
    width: 400px;
  }
  .box{
  float: left;
  }
  i{
    
    position: absolute;
    margin-top: 18px;
    margin-left: 370px;
  }
</style>
