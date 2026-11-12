<svelte:options customElement="name-sync" />

<script lang="ts">
    let value = $state("");
</script>

<div>
    <input bind:value={value} /> <p>{value}</p>
</div>