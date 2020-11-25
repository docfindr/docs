---
doc: 'Alpine JS'
title: '$nextTick'
slug: 'next-tick'
order: 5
section: 'Magic Properties'
section_order: 2
---

# `$nextTick`

Execute a given expression AFTER Alpine has made its reactive DOM updates.

**Example:**

```html
<div x-data="{ fruit: 'apple' }">
    <button
        x-on:click="
            fruit = 'pear';
            $nextTick(() => { console.log($event.target.innerText) });
        "
        x-text="fruit"
    ></button>
</div>
```

`$nextTick` is a magic property that allows you to only execute a given expression AFTER Alpine has made its reactive DOM updates. This is useful for times you want to interact with the DOM state AFTER it's reflected any data updates you've made.