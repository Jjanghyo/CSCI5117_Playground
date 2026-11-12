<svelte:options customElement="cat-fact" />

<script lang="ts">
    let res = $state("");

    async function get_response() {
		const response = await fetch('https://catfact.ninja/fact');
		let tmp = await response.json();
        res = tmp["fact"]
    }
</script>

<button onclick={get_response}>Click</button>
<p>{res}</p>