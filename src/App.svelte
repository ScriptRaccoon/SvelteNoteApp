<script>
    import Header from "./components/Header.svelte";
    import Controls from "./components/Controls.svelte";
    import Note from "./components/Note.svelte";
    import Input from "./components/Input.svelte";
    import { v4 as uuidv4 } from "uuid";
    $: inputVisible = false;
    $: notes = [
        {
            id: 0,
            created: new Date(),
            content: "Handyvertrag kündigen",
        },
        {
            id: 1,
            created: new Date(),
            content: "PC neu installieren",
        },
    ];

    function deleteNote(e) {
        const id = e.detail;
        notes = notes.filter((note) => note.id != id);
    }

    function showInput() {
        inputVisible = !inputVisible;
    }
    function newNote(e) {
        inputVisible = false;
        const note = {
            id: uuidv4(),
            created: new Date(),
            content: e.detail,
        };
        notes = [...notes, note];
        console.log(notes);
    }
</script>

<Header />

<main>
    <Controls on:showInput={showInput} />
    {#if inputVisible}
        <Input on:newNote={newNote} />
    {/if}
    <div class="noteContainer">
        {#each notes as note (note.id)}
            <Note {note} on:delete={deleteNote} />
        {/each}
    </div>
</main>

<style>
    main {
        max-width: 800px;
        margin: 0 auto;
        padding: 20px;
    }
    .noteContainer {
        padding: 10px;
        display: flex;
        flex-wrap: wrap;
    }
</style>
