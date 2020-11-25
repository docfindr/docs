---
doc: 'Alpine JS'
title: 'x-init'
slug: 'x-init'
order: 2
section: 'Directives'
section_order: 1
---

# `x-init`

Runs an expression when a component is initialized.

**Example:** 

```html
<div x-data="{ foo: 'bar' }" x-init="foo = 'baz'"></div>
```

**Structure:** 

```html
<div x-data="..." x-init="[expression]"></div>
```

`x-init` runs an expression when a component is initialized.

If you wish to run code AFTER Alpine has made its initial updates to the DOM (something like a `mounted()` hook in VueJS), you can return a callback from `x-init`, and it will be run after:

```x-init="() => { // we have access to the post-dom-initialization state here // }"```