<script>
    import { onMount } from "svelte";
    import { writable } from "svelte/store";

    let input1 = "";
    let input2 = "";
    let input3 = "";
    let data = writable([]);

    const saveData = () => {
        const newData = {
            field1: input1,
            field2: input2,
            field3: input3,
        };
        data.update((prevData) => [...prevData, newData]);
        // Reset input fields
        input1 = "";
        input2 = "";
        input3 = "";
    };

    onMount(() => {
        // Uncomment the following line to prepopulate the data array with some initial values
        // data.set([{ field1: "Value 1", field2: "Value 2", field3: "Value 3" }]);
    });
</script>

<div class="main_div">
    <div>
        <label for="input1">Input 1:</label>
        <input type="text" id="input1" bind:value={input1} />
    </div>
    <div>
        <label for="input2">Input 2:</label>
        <input type="text" id="input2" bind:value={input2} />
    </div>
    <div>
        <label for="input3">Input 3:</label>
        <input type="text" id="input3" bind:value={input3} />
    </div>
    <div>
    <button on:click={saveData}>Save</button>
    </div>
</div>

<ul>
    {#each $data as item}
        <li>{item.field1} - {item.field2} - {item.field3}</li>
    {/each}
</ul>

<style>
    .main_div {
       display: flex;
       flex-direction: column;
       justify-content: center;
    }
</style>
