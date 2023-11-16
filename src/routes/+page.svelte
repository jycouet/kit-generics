<script lang="ts">
  import Form from "$lib/Form.svelte";
  import { get } from "svelte/store";
</script>

<svelte:head>
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/water.css@2/out/dark.css"
  />
</svelte:head>

<h1>Welcome to SvelteKit</h1>

<h2>First</h2>
<Form init={{ name: "JYC", age: 37 }} />

<h2>Second</h2>
<Form init={{ name: "JYC", age: 37 }}>
  <svelte:fragment slot="custom" let:initStore>
    Custom
    <pre>{JSON.stringify(get(initStore))}</pre>
  </svelte:fragment>
</Form>
