<script>
  import { scale, fade } from "svelte/transition";
  import { FeedbackStore } from "../stores";
  import FeedbackItem from "./FeedbackItem.svelte";
</script>

{#each $FeedbackStore as fb (fb.id)}
  <div in:scale out:fade>
    <FeedbackItem item={fb} />
  </div>
{/each}
