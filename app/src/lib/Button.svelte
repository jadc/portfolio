<script lang="ts">
    let { icon="", label="Button", href="#" } = $props();
</script>

<a class="
    inline-flex gap-2 px-4 py-2
    bg-zinc-900 text-white rounded-full
    border border-zinc-800 hover:border-zinc-700
    "
    href="{href}">
    {#if icon}<img class="inline w-6 aspect-square" src="icons/{icon}.svg" alt="Icon"/>{/if}
    <p>{label}</p>
</a>
