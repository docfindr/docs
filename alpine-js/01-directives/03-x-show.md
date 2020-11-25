---
doc: 'Alpine JS'
title: 'x-show'
slug: 'x-show'
order: 3
section: 'Directives'
section_order: 1
---

# `x-show`

Toggles `display: none;` on the element depending on expression (true or false).

**Example:** 

```html
<div x-show="open"></div>
```

**Structure:** 

```html
<div x-show="[expression]"></div>
```

`x-show` toggles the `display: none;` style on the element depending if the expression resolves to `true` or `false`.

**x-show.transition**

`x-show.transition` is a convenience API for making your `x-show`s more pleasant using CSS transitions.

```html
<div x-show.transition="open">
    These contents will be transitioned in and out.
</div>
```

| Directive                                               | Description |
| ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `x-show.transition`                                     | A simultaneous fade and scale. (opacity, scale: 0.95, timing-function: cubic-bezier(0.4, 0.0, 0.2, 1), duration-in: 150ms, duration-out: 75ms) |
| `x-show.transition.in`                                  | Only transition in.                                                                                                                            |
| `x-show.transition.out`                                 | Only transition out.                                                                                                                           |
| `x-show.transition.opacity`                             | Only use the fade.                                                                                                                             |
| `x-show.transition.scale`                               | Only use the scale.                                                                                                                            |
| `x-show.transition.scale.75`                            | Customize the CSS scale transform `transform: scale(.75)`.                                                                                     |
| `x-show.transition.duration.200ms`                      | Sets the "in" transition to 200ms. The out will be set to half that (100ms).                                                                   |
| `x-show.transition.origin.top.right`                    | Customize the CSS transform origin `transform-origin: top right`.                                                                              |
| `x-show.transition.in.duration.200ms.out.duration.50ms` | Different durations for "in" and "out".                                                                                                        |

> All of these transition modifiers can be used in conjunction with each other. This is possible (although ridiculous lol): `x-show.transition.in.duration.100ms.origin.top.right.opacity.scale.85.out.duration.200ms.origin.bottom.left.opacity.scale.95`

> `x-show` will wait for any children to finish transitioning out. If you want to bypass this behavior, add the `.immediate` modifer:

```html
<div x-show.immediate="open">
    <div x-show.transition="open">
</div>
```