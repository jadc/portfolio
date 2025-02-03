<script lang="ts">
    import { page } from "$app/state";

	import Button from "$lib/Button.svelte"

	let { showBg } = $props();

	let nav = [
        { name: "Home",       href: "/" },
        { name: "Projects",   href: "/projects" },
        { name: "Experience", href: "/experience" },
        { name: "Posts",      href: "/posts" },
    ];

    function onclick() {
        console.log("todo");
    }
</script>

<nav class="
        sticky top-4 p-2 z-50 inset-x-0 mx-auto w-fit
        flex gap-2 justify-center items-center
        rounded-full { showBg ? 'bg-black/20 backdrop-blur-xs ' : 'bg-main-950/0'} duration-500 ease-in-out
        ">
    {#each nav as x (x.href)}
        <Button {onclick} active={page.url.pathname === x.href} label={x.name} href={x.href} icon="github"/>
    {/each}
</nav>
