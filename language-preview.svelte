<svelte:head>
  <title>Language Svelte</title>
</svelte:head>

<svelte:body on:click={handleBodyClick} />

{#if paragraph}
  <p class="">{@html paragraph}</p>

{:else if Svelte}
  <p>There is no para&shy;graph...But here is, ...</p>
  <Svelte />!
{/if}

<LongComponentName />
<ComponentWithChildcomponents.Child />

{#each items as item}

  {#if item.props}
    <svelte:component this={item}>
  {:else}
    <p>“{ item }” may just be a plain string.</p>
  {/if}

{:else}
  <Svelte on:click { items.length ? 'yes' : 'no' } />
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
  import LongComponentName from './LongComponentName.svelte';
  import * from './ComponentWithChildcomponents.svelte';

  export let paragraph = 'Hello Svelte';
  export let items = [];

  const Immovable = 'Flex 💪';

  $: withName = `Rvantonisse says: ${paragraph}`;
</script>
