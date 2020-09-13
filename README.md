# Language Svelte

> HTML (Svelte)

Provides syntax highlighting for Svelte Components, directives and other Svelte specific syntax in Atom.

Initial extracted grammar from [ide-svelte](https://github.com/sveltejs/svelte-atom), by [UnwrittenFun](https://github.com/UnwrittenFun). If you are looking for IDE support use that instead.

## Features

... Svelte syntax highlighting without the advanced IDE ...

- Html autocompletion support from atom/language-html
- Svelte snippets for: {#if}, {#each}, {#await} and `<svelte:tag>`.

## Why?...

I like getting color in my code. I even get distracted when there is syntax not being colored! Creating syntax themes are one thing, creating or contributing to a grammar gives the possibility to add more detailed scopes. Adding more squares to paint in! 👨‍🎨 On top of that, creating my own package gives me full control. 🤓

## Roadmap to v1.0.0

- [ ] Refinement to scope naming, using naming conventions from [Sublime](https://www.sublimetext.com/docs/3/scope_naming.html) and [TextMate](https://macromates.com/manual/en/language_grammars#naming_conventions).

  - [ ] Add support scopes on svelte specific stuff; (`svelte:xxx`, `{@html|debug}` tags, customized handlebar templating blocks `{#if} {:else}`, naming some)

    - [x] Template blocks

  - [ ] Add / duplicate the nice tag scope naming refinment from language-html (including `text.html.basic` top-level works but may overwrite with svelte scopes)

- [ ] Snippets? Auto-completion?

- [ ] Tree sitter Svelte... This seems to be a bit more advanced stuff...
