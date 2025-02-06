<script lang="ts">
	import "../app.css";
	let { children } = $props();

    // Subcomponents
	import Header from "$lib/Header.svelte"
	import Footer from "$lib/Footer.svelte"
	import Background from "$lib/Background.svelte"
</script>

<Background/>
<Header/>
<div class="relative w-screen max-w-full bg-main-700/80 backdrop-blur-xs">
    <main class="max-w-screen-lg mx-auto md:py-4">
        {@render children()}
    </main>
</div>
<Footer/>
