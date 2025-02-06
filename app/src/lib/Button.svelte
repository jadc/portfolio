<script lang="ts">
    let { icon="", label="", active=false, ...props } = $props();
</script>

<a {...props} class="
    inline-flex gap-2 px-4 py-2
    text-white rounded-full border transition-colors
    {active ? 'border-main-700 bg-main-700' : 'border-main-900 hover:border-main-700 bg-main-900 '}
    ">
    {#if icon}<img class="inline w-6 aspect-square" src="icons/{icon}.svg" alt="Icon"/>{/if}
    {#if label}{label}{/if}
</a>
