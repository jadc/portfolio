<script lang="ts">
	import Button from "$lib/Button.svelte"

	let { name } = $props();

	let nav = [
        { name: "Projects",   href: "/projects" },
        { name: "Experience", href: "/jobs" },
        { name: "Posts",      href: "/posts" },
    ];
</script>

<nav class="sticky top-4 py-2 z-50 max-w-screen-lg inset-x-0 mx-auto flex gap-2 justify-center items-center rounded-full bg-zinc-900 bg-opacity-80 backdrop-blur-sm">
    <div class="absolute left-10 flex items-center gap-3">
        <img class="w-10" src="icons/jad.svg" alt="{name}">
        <h1 class="text-white">{name}</h1>
    </div>
    {#each nav as page (page.href)}
        <Button label={page.name} href={page.href} icon="github"/>
    {/each}
</nav>
