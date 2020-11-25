---
doc: 'Alpine JS'
title: 'x-spread'
slug: 'x-spread'
order: 13
section: 'Directives'
section_order: 1
---

# `x-spread`

Allows you to bind an object of Alpine directives to an element for better reusability.

**Example:**

```html
<div x-data="dropdown()">
    <button x-spread="trigger">Open Dropdown</button>

    <span x-spread="dialogue">Dropdown Contents</span>
</div>

<script>
    function dropdown() {
        return {
            open: false,

            trigger: {
                ['@click']() {
                    this.open = true;
                }
            },

            dialogue: {
                ['x-show']() {
                    return this.open;
                },

                ['@click.away']() {
                    this.open = false;
                }
            }
        }
    }
</script>
```

`x-spread` allows you to extract an element's Alpine bindings into a reusable object.

The object keys are the directives (Can be any directive including modifiers), and the values are callbacks to be evaluated by Alpine.

There are a couple of caveats to x-spread:
- When the directive being "spread" is `x-for`, you should return a normal expression string from the callback. For example: `['x-for']() { return 'item in items' }`.
- `x-data` and `x-init` can't be used inside a "spread" object.