---
doc: 'Alpine JS'
title: 'x-data'
slug: 'x-data'
order: 1
section: 'Directives'
section_order: 1
---

# `x-data`

Declares a new component scope.

**Example:** 

```html
<div x-data="{ foo: 'bar' }">...</div>
```

**Structure:** 

```html
<div x-data="[object literal]">...</div>
```

`x-data` declares a new component scope. It tells the framework to initialize a new component with the following data object.

Think of it like the `data` property of a Vue component.

## Extract Component Logic

You can extract data (and behavior) into reusable functions:

```html
<div x-data="dropdown()">
    <button x-on:click="open">Open</button>

    <div x-show="isOpen()" x-on:click.away="close">
        // Dropdown
    </div>
</div>

<script>
    function dropdown() {
        return {
            show: false,
            open() { this.show = true },
            close() { this.show = false },
            isOpen() { return this.show === true },
        }
    }
</script>
```

> For bundler users, note that Alpine.js accesses functions that are in the global scope (`window`), you'll need to explicitly assign your functions to `window` in order to use them with `x-data` for example `window.dropdown = function () {}` (this is because with Webpack, Rollup, Parcel etc. `function`'s you define will default to the module's scope not `window`).

You can also mix-in multiple data objects using object destructuring:

```html
<div x-data="{...dropdown(), ...tabs()}">
```