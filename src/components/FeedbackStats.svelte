<script>
    import { FeedbackStore } from "../stores";

    $: count = $FeedbackStore ? $FeedbackStore.length : 0;
    $: average = $FeedbackStore && count ? $FeedbackStore.reduce((a, {rating}) =>
        a + rating, 0) / count : 0;
</script>

<div class="feedback-stats">
    <h4>{count} Reviews</h4>
    <h4>Rating Average: {average}</h4>
</div>

<style>
    .feedback-stats {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
</style>