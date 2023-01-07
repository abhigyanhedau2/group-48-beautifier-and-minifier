<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let type = "primary";
  const clickHandler = () => {
    dispatch("clickEvent");
  };
</script>

<button class={type} on:click={clickHandler}><slot /></button>

<style>
.primary{
  width: 100px;
  margin: 20px 40px;
  background-color: #0066ff;
  color: white;
  border-radius: 8px;
  border: 1px solid #D8D8DA;
  font-size: 16px;
  padding: 8px 14px;
  height: auto;
  transition: 1s;
  }
.primary:hover{
  transform: scale(1.1);
  z-index:3;
}

</style>
