---
doc: 'Alpine JS'
title: '$event'
slug: 'event'
order: 3
section: 'Magic Properties'
section_order: 2
---

# `$event`

Retrieve the native browser "Event" object within an event listener.

**Example:**

```html
<input x-on:input="alert($event.target.value)">
```

`$event` is a magic property that can be used within an event listener to retrieve the native browser "Event" object.

> The $event property is only available in DOM expressions.

If you need to access $event inside of a JavaScript function you can pass it in directly:

`<button x-on:click="myFunction($event)"></button>`