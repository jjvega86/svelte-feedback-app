<!-- 
import { onMount, onDestroy } from "svelte";
let feedback = [];

const unsubscribe = FeedbackStore.subscribe((data) => (feedback = data));

onDestroy(() => {
  unsubscribe();
});

 -->
<script>
  import { FeedbackStore } from "../store/stores";
  import { fade, scale } from "svelte/transition";
  import FeedbackItem from "./FeedbackItem.svelte";
</script>

<!-- * LONG WAY TO SUBSCRIBE/UNSUBSCRIBE TO A STORE ABOVE -->

{#each $FeedbackStore as item (item.id)}
  <div in:scale out:fade={{ duration: 500 }}>
    <FeedbackItem {item} />
  </div>
{/each}
