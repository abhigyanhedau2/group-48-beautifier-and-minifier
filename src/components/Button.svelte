<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let type = "primary";
  const clickHandler = () => {
    dispatch("clickEvent");
  };
</script>

<button class={type} on:click={clickHandler}><slot /></button>

<style></style>
