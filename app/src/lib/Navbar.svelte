<script lang="ts">
	import Button from "$lib/Button.svelte"
	let props = $props();
	let nav = [
        { name: "Projects",   href: "/projects" },
        { name: "Experience", href: "/jobs" },
        { name: "Posts",      href: "/posts" },
    ];
</script>

<nav {...props}>
    {#each nav as page (page.href)}
        <Button label={page.name} href={page.href} icon="github"/>
    {/each}
</nav>
