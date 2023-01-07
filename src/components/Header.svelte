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
  <h1>{heading}</h1>
  {#if hasHomeBtn}
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div  on:click={changePageHandler}>
      <i class="fa-solid fa-house" />
    </div>
  {/if}
  
</header>

<style>
  header{
    background-color: #0066FF;
    margin-left: -7px;
    margin-right: -6px;
   
  }
  h1{
    font-family: 'Inter', sans-serif;
    color:white;
    text-align: center;
    margin-top: -10px;
    margin-bottom:10px;
    margin-left: 10px;
    margin-right: -8px;
    padding-left: 10px;
    padding-top: 16px;
    padding-bottom: 16px;
    
  }
  i{
    
  }
</style>
