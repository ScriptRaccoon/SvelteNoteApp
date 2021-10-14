<script>
    import DeleteButton from "./DeleteButton.svelte";
    export let note;
</script>

<div class="note">
    <DeleteButton id={note.id} on:delete />
    {note.content}
</div>

<style>
    .note {
        border: none;
        outline: none;
        font-family: inherit;
        color: inherit;
        border-radius: 10px;
        width: 200px;
        height: 200px;
        padding: 15px;
        background-color: rgb(229, 198, 147);
        margin: 10px;
        position: relative;
    }
</style>
