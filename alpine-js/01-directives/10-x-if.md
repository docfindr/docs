---
doc: 'Alpine JS'
title: 'x-if'
slug: 'x-if'
order: 10
section: 'Directives'
section_order: 1
---

# `x-if`

Remove an element completely from the DOM. Needs to be used on a `<template>` tag.

**Example:** 

```html
<template x-if="true"><div>Some Element</div></template>
```

**Structure:** 

```html
<template x-if="[expression]"><div>Some Element</div></template>
```

For cases where `x-show` isn't sufficient (`x-show` sets an element to `display: none` if it's false), `x-if` can be used to  actually remove an element completely from the DOM.

It's important that `x-if` is used on a `<template></template>` tag because Alpine doesn't use a virtual DOM. This implementation allows Alpine to stay rugged and use the real DOM to work its magic.

> Note: `x-if` must have a single element root inside the `<template></template>` tag.

> Note: When using `template` in a `svg` tag, you need to add a [polyfill](https://github.com/alpinejs/alpine/issues/637#issuecomment-654856538) that should be run before Alpine.js is initialized.