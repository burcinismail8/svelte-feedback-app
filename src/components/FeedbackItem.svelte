<script>
  import { FeedbackStore } from "../stores";
  import Card from "./Card.svelte";
  export let item;
  const handleClose = (id) => {
    FeedbackStore.update((currentFeedback) => {
      return currentFeedback.filter((item) => item.id != id);
    });
  };
</script>

<Card>
  <div class="num-display">
    {item.rating}
  </div>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div class="close" on:click={() => handleClose(item.id)}>X</div>
  <div class="text-display">
    {item.text}
  </div>
</Card>

<style>
  .num-display {
    position: absolute;
    top: -10px;
    left: -10px;
    width: 50px;
    height: 50px;
    background: #ff6a95;
    color: #fff;
    border: 1px #eee solid;
    border-radius: 50%;
    padding: 10px;
    text-align: center;
    font-size: 19px;
  }
  .close {
    position: absolute;
    top: 10px;
    right: 20px;
    cursor: pointer;
    background: none;
    border: none;
  }
</style>
