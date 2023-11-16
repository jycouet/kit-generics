<script lang="ts">
  export let init: any = {};

  let list = Object.entries(init).map(([key, value]) => ({ key, value }));
</script>

{#each list as { key, value }, i}
  <div>
    <label>
      <input bind:value />
      {key}
    </label>
  </div>
{/each}
