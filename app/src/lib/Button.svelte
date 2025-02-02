<script lang="ts">
    let { icon="", label="", href="#", active=false } = $props();
</script>

<a class="
    inline-flex gap-2 px-4 py-2
    text-white rounded-full border
    {active ? 'border-white bg-sky' : 'border-zinc-800 hover:border-zinc-700 bg-zinc-900 '}
    "
    href="{href}">
    {#if icon}<img class="inline w-6 aspect-square" src="icons/{icon}.svg" alt="Icon"/>{/if}
    {#if label}{label}{/if}
</a>
