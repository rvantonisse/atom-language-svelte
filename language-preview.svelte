<!--
 * @component
 *
 * # Preview.svelte
 *
 * A preview component for all Svelte syntax
 * -->
<svelte:options type="">

<svelte:window on:event={handleEvent}>

<svelte:head>
  <title>Preview.svelte</title>
  <meta name="description" content="A preview component for all Svelte syntax">

  <link rel="stylesheet" href="/css/Preview.css">
</svelte:head>

<svelte:body on:event={handleEvent}>

<svelte:component {value} title={Component} bind:group={Component}>

<svelte:self prop={value}>

<!-- a regular HTML element -->
<div class="container" class:focus="{isFocussed}">

  <!-- a component -->
	<Class id="Widget" value="{foo ? bar : baz}"/>
  <LongClass />
  <Class2 />

  <Namespace.Class />
  <namespace.class />

  <custom-element />
  <custoM-ElemenT1000 />
  <CustoM-ElemenT2000 />

  <Class.Attributes
    id="{id}"
    class="Class"
    {shorthand}
    boolean
    on:event
    on:otherEvent={withHandler}
    bind:property={propertyValue}
    bind:propShorthand
    bind:this={Component}
  />

  <tag-directives
    on:event|preventDefault|stopPropagation|passive|capture|once|self="{handleEvent}"
    on:componentEvent
    bind:property={propertyValue}
    bind:value
    bind:group={variable}
    bind:this={domNode}
    class:someClass
    class:otherClass={someBooleanValue}
    use:action
    use:action={withParameters}
  />

  <otherTag/>
</div>

{#if expression}
  {expression}
{:else if !expression}
  {!expression}
{:else}
  <p>Something else</p>
{/if}

{#each expression as name, index (key)}
  <p>{name} {index} - ({key})</p>
{:else}
  <p>Something else</p>
{/each}

{#await promise}
	<!-- promise is pending -->
	<p>waiting for the promise to resolve...</p>
{:then value}
	<!-- promise was fulfilled -->
	<p {value}>The value is {value}</p>
{:catch error}
	<!-- promise was rejected -->
	<p>Something went wrong: {error.message}</p>
{/await}

<!--
 * If you don't care about the pending state,
 * you can also omit the initial block
 * -->
{#await promise then value}
	<p>The value is {value}</p>
{/await}

<!-- @html -->
<div {id} class="blog-post">
	<h1>{post.title}</h1>

	{@html post.content}
</div>

{@debug foo}

<style>
  :global(div) {
    color: hotpink;
  }

  body {
    color: black;
    background-color: white;
  }

  @keyframes -global-my-global-animation-name {
    0% {
      opacity: 1;
    }

    100% {
      opacity: 0;
    }
  }

  @keyframes my-local-animation-name {
    0% {
      opacity: 1;
    }

    100% {
      opacity: 0;
    }
  }
</style>

<script>
  import Widget from './Widget.svelte';
	import * from './Namespace.svelte';

  export let bar = 'optional default initial value';
  export let baz = undefined;

  // these are readonly
	export const thisIs = 'readonly';

	export function greet(name) {
		alert(`hello ${name}!`);
	}

	// this is a prop
	export let format = (n) => n.toFixed(2);

  let className;

	// creates a `class` property, even
	// though it is a reserved word
	export { className as class };

	// Values that are passed in as props
  export let foo;

	// are immediately available
	console.log({ foo });

  let count = 0;

  function handleClick () {
    // calling this function will trigger an
    // update if the markup references `count`
    count = count + 1;
  }

  export let title;

  // this will update `document.title` whenever
  // the `title` prop changes
  $: document.title = title;

  $: {
    console.log(`multiple statements can be combined`);
    console.log(`the current title is ${title}`);
  }

  export let num;

  // we don't need to declare `squared` and `cubed`
  // — Svelte does it for us
  $: squared = num * num;
  $: cubed = squared * num;
</script>

<script context="module">
  export function someExportedFunction(args) {
    const { one, two } = args;

    return one + two;
  }
</script>
