<script>
    export let title = "제목";
    export let id;
    export let val;
    export let cdSet;
    export let validateYn = true;
    // console.log("Select.svelte");
</script>

<label for="{id}" class="form-label">{title}</label>
<select class="form-select" bind:value={val} id="{id}" name="{id}" aria-label="" required={validateYn}>
{#each cdSet as code, i}
    <option value="{code.id}">{code.name}</option>
{/each}
</select>