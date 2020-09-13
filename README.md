# Language Svelte

> HTML (Svelte)

Provides syntax highlighting for Svelte Components, directives and other Svelte specific syntax in Atom.

If you are looking for IDE support use [ide-svelte](https://github.com/sveltejs/svelte-atom) instead.

## Syntax naming conventions

Syntax naming is done following conventions from [Sublime](https://www.sublimetext.com/docs/3/scope_naming.html) and [TextMate](https://macromates.com/manual/en/language_grammars#naming_conventions).


## Features

- Html snippet / autocompletion support from atom/language-html
- Svelte snippets for: {#if}, {#each}, {#await} and `<svelte:tag>`.

## Roadmap to v1.0.0

- [ ] All Svelte syntax captured:

  - [x] Template blocks; if, each, await.

  - [ ] `{expression}` - Svelte expressions

  - [x] `<svelte:tag>`

  - [x] `<Component/>` (tag.component)

  - [ ] Element directives:

    - [ ] on - event directive
    - [ ] bind - data flow directives
    - [ ] class - css classes directive
    - [ ] use - action directive
    - [ ] transition|animate|in|out - motion directives

  - [ ] Component directives; on, bind.

  - [ ] Svelte component lifecycle

  - [ ] Svelte slot element; named slot, slot property values

  - [ ] Svelte modules; stores, motion, transition, animation

- [x] Snippets

- [ ] Tree sitter Svelte... This seems to be a bit more advanced stuff and might be done in v1.1+.
