<script>
    //polls from PollStore
	import PollStore from '../stores/PollStore.js';
    import PollDetails from "./PollDetails.svelte";

    import { fade, slide, scale } from 'svelte/transition';
    import { flip } from 'svelte/animate';


    //export let polls = []

    // const unsub = PollStore.subscribe( (data) => {
    //     polls = data;
    // });

    // //onMount
    // onMount(() => {
    //     //maybe get data from the db
        
    // });

    // onDestroy(() => {
    //     //unsubscribe from Store
    //     unsub();
    // });


</script>

<div class="poll-list">
    {#each $PollStore as poll (poll.id)}
        <div in:fade out:scale|local animate:flip={{duration: 500}}>
            <PollDetails {poll} />
        </div>
    {/each}
</div>

<style>
    .poll-list{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
    }
</style>