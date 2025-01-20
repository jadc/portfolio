<script lang="ts">
    let props = $props();
	let nav = [
        { label: "Projects", route: "/projects" },
        { label: "Experience", route: "/jobs" },
        { label: "Posts", route: "/posts" },
    ];
	let external = [
        { label: "GitHub", route: "https://github.com/jadc" },
        { label: "Linkedin", route: "https://www.linkedin.com/in/jad-c" },
        { label: "Resume", route: "/resume" },
    ];
</script>

<div {...props}>
    <header class="flex">
        <img class="w-1/4" src="https://jad.red/jad.svg" alt="Jad Chehimi">
        <aside class="grid">
            <div>
                <h1 class="text-2xl">Jad Chehimi</h1>
                <h2>Software Developer</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
            </div>
            <nav class="flex gap-2">
                {#each external as site (site.route)}
                    <a class="bg-zinc-900 px-5 py-2 border border-zinc-800 hover:border-zinc-700 rounded-full" href="{site.route}">{site.label}</a>
                {/each}
            </nav>
        </aside>
    </header>

    <nav class="flex w-full gap-2 justify-center">
        {#each nav as page (page.route)}
            <a class="px-5 py-2 border-b border-transparent hover:border-white" href="{page.route}">{page.label}</a>
        {/each}
    </nav>
</div>
