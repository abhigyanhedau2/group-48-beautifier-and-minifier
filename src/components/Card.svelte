<script></script>

<div class="card-wrapper">
  <slot />
</div>

<style>
  .card-wrapper {
    padding: 24px 24px 24px 24px;
    height: 160px;
    width: 160px;
    border: 0px solid black;
    margin-left: 80px;
    margin-right: 80px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    border-radius: 10px;
    text-align: center;
    font-size: 20px;
    margin-top: 8px;

    font-family: "Inter", sans-serif;
    box-shadow: 4px 4px 12px black;
    transition: 0.25s;
    background-color: black;
  }
  .card-wrapper:hover {
    transform: scale(1.1);
    z-index: 3;
  }
</style>
