---
doc: 'Alpine JS'
title: '$watch'
slug: 'watch'
order: 6
section: 'Magic Properties'
section_order: 2
---

# `$watch`

Will fire a provided callback when a component property you "watched" gets changed.

**Example:**

```html
<div x-data="{ open: false }" x-init="$watch('open', value => console.log(value))">
    <button @click="open = ! open">Toggle Open</button>
</div>
```

You can "watch" a component property with the `$watch` magic method. In the above example, when the button is clicked and `open` is changed, the provided callback will fire and `console.log` the new value.