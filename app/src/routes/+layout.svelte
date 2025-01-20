<script lang="ts">
	import "../app.css";
	let { children } = $props();

	import Sidebar from "$lib/Sidebar.svelte"
</script>

<div class="flex w-screen h-screen overflow-hidden bg-orange-600">
    <Sidebar class="bg-red-600"/>
    <main>
        {@render children()}
    </main>
    <footer>
        <p>Footer text</p>
    </footer>
</div>
