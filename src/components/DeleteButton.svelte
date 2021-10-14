<script>
    export let id;
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
    function deleteNote() {
        dispatch("delete", id);
    }
</script>

<button class="deleteButton" on:click={deleteNote}>x</button>

<style>
    .deleteButton {
        position: absolute;
        top: 0;
        right: 0;
        cursor: pointer;
        background: rgb(182, 59, 37);
        height: 20px;
        width: 20px;
        font-size: 14px;
        color: white;
        border: none;
    }
</style>
