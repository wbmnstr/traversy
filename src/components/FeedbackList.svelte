<script>
    //import {onMount, onDestroy} from 'svelte';
    import {FeedBackStore} from '../stores';
    import { fade, scale, blur, slide } from 'svelte/transition';
    import FeedbackItem from './FeedbackItem.svelte';

/*
    let feedback=[];
    const unsubscribe=FeedBackStore.subscribe(data=>feedback=data);

    onMount(()=>{
        console.log('mounted');
    });

    onDestroy(()=>{
        unsubscribe();
    });
*/
</script>

{#each $FeedBackStore as fb (fb.id)}

<div in:slide out:fade>
    <FeedbackItem item={fb} />
</div>

{/each}