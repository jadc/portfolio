<script lang="ts">
	import "../app.css";
	let { children } = $props();

	import Navbar from "$lib/Navbar.svelte"
</script>

<div class="w-screen h-screen bg-black">
    <Navbar class="max-w-screen-lg m-auto p-10 bg-slate-900 text-white"/>
    <main class="max-w-screen-lg m-auto p-10 bg-orange-400">
        {@render children()}
    </main>
</div>
