---
doc: 'Alpine JS'
title: 'x-transition'
slug: 'x-transition'
order: 12
section: 'Directives'
section_order: 1
---

# `x-transition`

Directives for applying classes to various stages of an element's transition.

**Example:**

```html
<div
    x-show="open"
    x-transition:enter="transition ease-out duration-300"
    x-transition:enter-start="opacity-0 transform scale-90"
    x-transition:enter-end="opacity-100 transform scale-100"
    x-transition:leave="transition ease-in duration-300"
    x-transition:leave-start="opacity-100 transform scale-100"
    x-transition:leave-end="opacity-0 transform scale-90"
>
    ...
</div>
```

```html
<template x-if="open">
    <div
        x-transition:enter="transition ease-out duration-300"
        x-transition:enter-start="opacity-0 transform scale-90"
        x-transition:enter-end="opacity-100 transform scale-100"
        x-transition:leave="transition ease-in duration-300"
        x-transition:leave-start="opacity-100 transform scale-100"
        x-transition:leave-end="opacity-0 transform scale-90"
    >
        ...
    </div>
</template>
```

> The example above uses classes from [Tailwind CSS](https://tailwindcss.com).

## Available directives

Alpine offers 6 different transition directives for applying classes to various stages of an element's transition between "hidden" and "shown" states. These directives work both with `x-show` AND `x-if`.

These behave exactly like VueJS's transition directives, except they have different, more sensible names:

| Directive      | Description                                                                                                                                          |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| `:enter`       | Applied during the entire entering phase.                                                                                                            |
| `:enter-start` | Added before element is inserted, removed one frame after element is inserted.                                                                       |
| `:enter-end`   | Added one frame after element is inserted (at the same time `enter-start` is removed), removed when transition/animation finishes.                   |
| `:leave`       | Applied during the entire leaving phase.                                                                                                             |
| `:leave-start` | Added immediately when a leaving transition is triggered, removed after one frame.                                                                   |
| `:leave-end`   | Added one frame after a leaving transition is triggered (at the same time `leave-start` is removed), removed when the transition/animation finishes. |