<script>
    import {FeedbackStore} from '../stores';
    import { fade, scale, blur, slide } from 'svelte/transition';
    import FeedbackItem from './FeedbackItem.svelte';
    let feedback=[];

    FeedbackStore.subscribe((data)=>feedback=data);
</script>

{#each feedback as fb (fb.id)}

<div in:slide out:fade>
    <FeedbackItem item={fb} on:delete-feedback />
</div>

{/each}