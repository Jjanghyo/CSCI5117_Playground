<svelte:options customElement="pop-goes" />

<script lang="ts">
    let {max = 10, onpop = ()=>{} } = $props();
    let count = $state(0);

    function increment() {
        count++;
        if (count > max) {
            count = max;
            onpop();
        }
    }
</script>

<button onclick={increment}>Count: {count}</button>