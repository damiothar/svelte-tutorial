<script>
  import SFeedbackForm from "./components/FeedbackForm.svelte";
  import SFeedbackStats from "./components/FeedbackStats.svelte";
  import SFeedbackList from "./components/FeedbackList.svelte";
  let feedbackList = [
    {
      id: 1,
      rating: 10,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
    },
    {
      id: 2,
      rating: 9,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
    },
    {
      id: 3,
      rating: 8,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
    },
  ];
  $: count = feedbackList.length;
  $: average = feedbackList.reduce((a, { rating }) => a + rating, 0) / count;
  const deleteFeedbackItem = (event) => {
    const id = event.detail;
    feedbackList = feedbackList.filter((item) => item.id !== id);
  };
</script>

<main class="container">
  <SFeedbackForm />
  <SFeedbackStats {count} {average} />
  <SFeedbackList {feedbackList} on:deleteFeedbackItem={deleteFeedbackItem} />
</main>
