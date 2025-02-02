<script lang="ts">
	import "../app.css";
	let { children } = $props();

    // Subcomponents
	import Header from "$lib/Header.svelte"
	import Footer from "$lib/Footer.svelte"
	import Background from "$lib/Background.svelte"

    // Transition between pages
    import { onNavigate } from '$app/navigation'

    onNavigate(nav => {
        if (!document.startViewTransition) return

        return new Promise((resolve) => {
            document.startViewTransition(async () => { resolve(); await nav.complete })
        })
    })
</script>

<Background/>
<div class="relative max-w-screen-lg mx-auto md:py-4">
    <Header/>
    {@render children()}
    <Footer/>
</div>
