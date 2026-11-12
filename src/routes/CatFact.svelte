<svelte:options customElement="cat-fact" />

<script lang="ts">
    let facts = $state([]);

    async function get_response() {
		const response = await fetch('https://catfact.ninja/fact');
		let tmp = await response.json();
        facts.push(tmp["fact"]);
    }
</script>

<button onclick={get_response}>Click</button>
<ul>
    {#each facts as fact}
        <li>{fact}</li>
    {/each}
</ul>