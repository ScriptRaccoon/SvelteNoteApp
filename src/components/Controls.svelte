<script>
    import Button from "./Button.svelte";
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
    function showInput() {
        dispatch("showInput");
    }
</script>

<div class="controls">
    <span on:click={showInput}>
        <Button text="Add new note" />
    </span>
</div>

<style>
    .controls {
        text-align: center;
    }
</style>
