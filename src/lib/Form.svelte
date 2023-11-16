<script lang="ts" generics="T extends Record<string, any>">
  import { writable } from "svelte/store";

  export let init: T = {};

  let list = Object.entries(init).map(([key, value]) => ({ key, value }));

  const initStore = writable(init);
</script>

{#if $$slots.custom}
  <slot name="custom" {initStore} />
{:else}
  {#each list as { key, value }, i}
    <div>
      <label>
        {key}
        <input bind:value />
      </label>
    </div>
  {/each}
{/if}
