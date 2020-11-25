---
doc: 'Alpine JS'
title: 'x-ref'
slug: 'x-ref'
order: 9
section: 'Directives'
section_order: 1
---

# `x-ref`

Convenient way to retrieve raw DOM elements out of your component.

**Example:** 

```html
<div x-ref="foo"></div><button x-on:click="$refs.foo.innerText = 'bar'"></button>
```

**Structure:** 

```html
<div x-ref="[ref name]"></div><button x-on:click="$refs.[ref name].innerText = 'bar'"></button>
```

`x-ref` provides a convenient way to retrieve raw DOM elements out of your component. By setting an `x-ref` attribute on an element, you are making it available to all event handlers inside an object called `$refs`.

This is a helpful alternative to setting ids and using `document.querySelector` all over the place.

> Note: you can also bind dynamic values for x-ref: `<span :x-ref="item.id"></span>` if you need to.