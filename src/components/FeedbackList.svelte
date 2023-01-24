<script>
  import SFeedbackItem from "./FeedbackItem.svelte";
  export let feedbackList;
</script>

{#each feedbackList as feedbackItem (feedbackItem.id)}
  <SFeedbackItem {feedbackItem} on:deleteFeedbackItem />
{/each}
