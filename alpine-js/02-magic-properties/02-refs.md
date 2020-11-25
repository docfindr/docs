---
doc: 'Alpine JS'
title: '$refs'
slug: 'refs'
order: 2
section: 'Magic Properties'
section_order: 2
---

# `$refs`

Retrieve DOM elements marked with `x-ref` inside the component.

**Example:**

```html
<span x-ref="foo"></span>

<button x-on:click="$refs.foo.innerText = 'bar'"></button>
```

`$refs` is a magic property that can be used to retrieve DOM elements marked with `x-ref` inside the component. This is useful when you need to manually manipulate DOM elements.