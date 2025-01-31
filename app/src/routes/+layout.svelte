<script lang="ts">
	import Navbar from "$lib/Navbar.svelte"
	import Button from "$lib/Button.svelte"

	const name = "Jad Chehimi";

	let external = [
        { name: "GitHub",   href: "https://github.com/jadc" },
        { name: "Linkedin", href: "https://www.linkedin.com/in/jad-c" },
        { name: "Resume",   href: "/resume" },
    ];

	import "../app.css";
	let { children } = $props();
</script>

<div class="relative max-w-screen-lg mx-auto md:py-4">
    <header class="flex flex-col md:flex-row p-10 gap-5 bg-slate-900 text-white rounded-b-xl md:rounded-xl">
        <img class="w-full md:w-1/4 max-w-md m-auto" src="icons/jad.svg" alt="{name}">
        <aside class="flex flex-col gap-2">
            <div>
                <h1 class="text-3xl font-semibold">{name}</h1>
                <h2 class="text-xl">Software Developer</h2>
            </div>
            <p class="text-justify">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </aside>
        <nav class="flex flex-row md:flex-col gap-2">
            {#each external as site (site.href)}
                <Button label={site.name} href={site.href} icon="github"/>
            {/each}
        </nav>
    </header>

    <Navbar {name}/>

    <main class="p-10 mt-20 bg-zinc-400">
        {@render children()}
    </main>
</div>
