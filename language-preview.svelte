<svelte:head>
  <title>Language Svelte</title>
</svelte:head>

{#if paragraph}
  <p class="">{@html paragraph}</p>
{:else if Svelte}
  <p>There is no para&shy;graph...But here is, ...</p>
  <Svelte>!
{/if}

{#each items as item}
  <svelte:component this={item}>
{:else if item == Svelte}
  <Svelte on:click>
{/each}

<slot></slot>

<style>
  p {
    margin-bottom: 3em;
  }
</style>

<script>
  import Svelte from './Svelte.svelte';

  export let paragraph = 'Hello Svelte';
</script>

<script context="module">
  import Svelte from './Svelte.svelte';

  export let paragraph = 'Hello Svelte';
  export let items = [];

  $: withName = `Rvantonisse says: ${paragraph}`;
</script>
