<script lang="ts">
	import Navbar from "$lib/Navbar.svelte"

	import "../app.css";
	let { children } = $props();
</script>

<div class="relative max-w-screen-lg m-auto bg-red-400 md:p-4">
    <Navbar class="fixed w-full mx-auto"/>
    <main class="p-10 bg-zinc-400">
        {@render children()}
    </main>
</div>
