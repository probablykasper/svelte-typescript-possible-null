<script lang="ts">
  import { onMount } from 'svelte'
  import Counter from './Counter.svelte'

  let count: number = 0
  onMount(() => {
    const interval = setInterval(() => count++, 1000)
    return () => clearInterval(interval)
  })
</script>

