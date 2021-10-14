<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
    import Button from "./Button.svelte";
    function submitNote() {
        const text = document.getElementById("noteInput").value;
        dispatch("newNote", text);
    }
</script>

<div class="inputContainer">
    <textarea id="noteInput" />
    <span on:click={submitNote}>
        <Button text="Submit" />
    </span>
</div>

<style>
    #noteInput {
        width: 100%;
        padding: 10px;
        border: 1px solid black;
        margin: 20px;
        background: white;
        outline: none;
        color: inherit;
        font-family: inherit;
        font-size: inherit;
    }
    .inputContainer {
        text-align: center;
    }
</style>
