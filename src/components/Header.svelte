<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let hasHomeBtn = false;
  export let heading = "";
  const changePageHandler = () => {
    dispatch("changePage");
  };
</script>

<header>
  
  {#if hasHomeBtn}
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div  on:click={changePageHandler}>
      <i class="fa-solid fa-house fa-xl" />
    </div>
  {/if}
  <h1>{heading}</h1>
  
</header>

<style>
  header{
    background-color: #0066FF;
    margin-left: -8px;
    margin-right: -6px;
   
  }
  h1{
    font-family: 'Inter', sans-serif;
    color:white;
    text-align: center;
    margin-top: -10px;
    margin-bottom:10px;
    margin-left: 16px;
    margin-right: -8px;
    padding-left: 10px;
    padding-top: 12px;
    padding-bottom: 16px;
  }
  i{
    color:white;
    position: absolute;
    margin-top: 30px;
    margin-left: 20px;
    margin-right: 20px;
  }
</style>
