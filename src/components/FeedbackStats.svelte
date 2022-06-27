<script>
  import { FeedbackStore } from "../store/stores";

  $: count = $FeedbackStore.length;
  $: average =
    $FeedbackStore.length > 0
      ? $FeedbackStore.reduce((total, item) => {
          return total + item.rating;
        }, 0) / count
      : 0;
</script>

<div class="feedback-stats">
  <h4>{count} Reviews</h4>
  <h4>Ratings Average: {average}</h4>
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
