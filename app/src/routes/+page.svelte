<script lang="ts">
    let count = $state(0);
</script>

<p>Counter! omg... {count}</p>
<button onclick={() => count++}>+</button>
<button onclick={() => count--}>-</button>
