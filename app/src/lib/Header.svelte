<script lang="ts">
	import Navbar from "$lib/Navbar.svelte"
	import Button from "$lib/Button.svelte"

    // Data (temporary)
    let name = "Jad Chehimi";
	let external = [
        { name: "GitHub",   href: "https://github.com/jadc" },
        { name: "Linkedin", href: "https://www.linkedin.com/in/jad-c" },
        { name: "Resume",   href: "/icons/jad.svg" },
    ];

    // States
    let header: HTMLElement;
	let showBg = $state(false);

    // Fade in nav bar when main header is scrolled past
    $effect(() => {
        if (!header) return;

        const observer = new IntersectionObserver(entries => {
            const [entry] = entries;
            showBg = !entry.isIntersecting;

        }, { threshold: 0 });
        observer.observe(header);

        return () => observer.disconnect();
    });
</script>

<header bind:this={header} class="flex flex-col md:flex-row p-10 gap-5 text-white rounded-b-3xl md:rounded-3xl bg-main-900/70 backdrop-blur-xs">
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
<Navbar {showBg} />
