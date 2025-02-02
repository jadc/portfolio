<script lang="ts">
	let { children } = $props();
</script>

<div class="text-white bg-900-red">
    {@render children?.()}
</div>
