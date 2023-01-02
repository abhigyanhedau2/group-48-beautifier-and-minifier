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
    <div on:click={changePageHandler}>
      <i class="fa-solid fa-house" />
    </div>
  {/if}
  <h1>{heading}</h1>
</header>

<style></style>
