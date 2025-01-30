<script lang="ts">
	import Button from "$lib/Button.svelte"
	let props = $props();
	let nav = [
        { name: "Projects",   href: "/projects" },
        { name: "Experience", href: "/jobs" },
        { name: "Posts",      href: "/posts" },
    ];
	let external = [
        { name: "GitHub",   href: "https://github.com/jadc" },
        { name: "Linkedin", href: "https://www.linkedin.com/in/jad-c" },
        { name: "Resume",   href: "/resume" },
    ];
</script>

<div {...props}>
    <header class="flex flex-col md:flex-row p-10 gap-5 bg-slate-900 text-white rounded-b-xl md:rounded-xl">
        <img class="w-full md:w-1/4 max-w-md m-auto" src="icons/jad.svg" alt="Jad Chehimi">
        <aside class="flex flex-col gap-2">
            <div>
                <h1 class="text-3xl font-semibold">Jad Chehimi</h1>
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

    <nav class="flex w-full gap-2 justify-center my-4">
        {#each nav as page (page.href)}
            <Button label={page.name} href={page.href} icon="github"/>
        {/each}
    </nav>
</div>
