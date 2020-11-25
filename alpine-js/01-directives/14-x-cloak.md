---
doc: 'Alpine JS'
title: 'x-cloak'
slug: 'x-cloak'
order: 13
section: 'Directives'
section_order: 1
---

# `x-cloak`

This attribute is removed when Alpine initializes. Useful for hiding pre-initialized DOM.

**Example:** 

```html
<div x-data="{}" x-cloak></div>
```

`x-cloak` attributes are removed from elements when Alpine initializes. This is useful for hiding pre-initialized DOM. It's typical to add the following global style for this to work:

```html
<style>
    [x-cloak] { display: none; }
</style>
```