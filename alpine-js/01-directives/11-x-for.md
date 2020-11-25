---
doc: 'Alpine JS'
title: 'x-for'
slug: 'x-for'
order: 11
section: 'Directives'
section_order: 1
---

# `x-for`

Create new DOM nodes for each item in an array. Needs to be used on a `<template>` tag.

**Example:**

```html
<template x-for="item in items" :key="item">
    <div x-text="item"></div>
</template>
```

> The `:key` binding is optional, but HIGHLY recommended.

`x-for` is available for cases when you want to create new DOM nodes for each item in an array. This should appear similar to `v-for` in Vue, with one exception of needing to exist on a `template` tag, and not a regular DOM element.

> `x-for` must have a single element root inside of the `<template></template>` tag.

> When using `template` in a `svg` tag, you need to add a [polyfill](https://github.com/alpinejs/alpine/issues/637#issuecomment-654856538) that should be run before Alpine.js is initialized.

## Index

If you want to access the current index of the iteration, use the following syntax:

```html
<template x-for="(item, index) in items" :key="index">
    <!-- You can also reference "index" inside the iteration if you need. -->
    <div x-text="index"></div>
</template>
```

## Previous and next item

If you want to access the array object (collection) of the iteration, use the following syntax:

```html
<template x-for="(item, index, collection) in items" :key="index">
    <!-- You can also reference "collection" inside the iteration if you need. -->

    <!-- Current item. -->
    <div x-text="item"></div>

    <!-- Same as above. -->
    <div x-text="collection[index]"></div>

    <!-- Previous item. -->
    <div x-text="collection[index - 1]"></div>

    <!-- Next item -->
    <div x-text="collection[index + 1]"></div>
</template>
```

## Nesting `x-for`s

You can nest `x-for` loops, but you MUST wrap each loop in an element. For example:

```html
<template x-for="item in items">
    <div>
        <template x-for="subItem in item.subItems">
            <div x-text="subItem"></div>
        </template>
    </div>
</template>
```

## Iterating over a range

Alpine supports the `i in n` syntax, where `n` is an integer, allowing you to iterate over a fixed range of elements.

```html
<template x-for="i in 10">
    <span x-text="i"></span>
</template>
```