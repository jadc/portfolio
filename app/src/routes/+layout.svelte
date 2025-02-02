<script lang="ts">
	import "../app.css";
	let { children } = $props();

    // Subcomponents
	import Header from "$lib/Header.svelte"
	import Background from "$lib/Background.svelte"

    // States
	const name = "Jad Chehimi";
</script>

<Background/>
<div class="relative max-w-screen-lg mx-auto md:py-4">
    <Header {name} />
    <main class="p-10 mt-20 bg-zinc-400">
        {@render children()}
    </main>
</div>
