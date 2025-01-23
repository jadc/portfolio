<script lang="ts">
	import Navbar from "$lib/Navbar.svelte"

	import "../app.css";
	let { children } = $props();
</script>

<div class="w-screen h-screen bg-black md:p-4">
    <Navbar/>
    <main class="max-w-screen-lg m-auto p-10 bg-orange-400">
        {@render children()}
    </main>
</div>
