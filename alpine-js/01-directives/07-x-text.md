---
doc: 'Alpine JS'
title: 'x-text'
slug: 'x-text'
order: 7
section: 'Directives'
section_order: 1
---

# `x-text`

Works similarly to `x-bind`, but will update the `innerText` of an element.

**Example:** 

```html
<span x-text="foo"></span>
```

**Structure:** 

```html
<span x-text="[expression]"
```

`x-text` works similarly to `x-bind`, except instead of updating the value of an attribute, it will update the `innerText` of an element.