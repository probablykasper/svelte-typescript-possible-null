<script lang="ts">
  type User =  { name: any } | null
  let user: User = {
    name: new Promise((resolve) => {
      setTimeout(() => {
        resolve('probablykasper')
      }, 1000)
    })
  }
</script>

{#if user}
  {#await user.name}
    Loading username
  {:then name}
    Username: {name}
  {/await}
{/if}
