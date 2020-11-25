---
doc: 'Alpine JS'
title: 'x-bind'
slug: 'x-bind'
order: 4
section: 'Directives'
section_order: 1
---

# `x-bind`

Sets the value of an attribute to the result of a JS expression.

> You are free to use the shorter ":" syntax: `:type="..."`.

**Example:** 

```html
<input x-bind:type="inputType">
```

**Structure:** 

```html
<input x-bind:[attribute]="[expression]">
```

`x-bind` sets the value of an attribute to the result of a JavaScript expression. The expression has access to all the keys of the component's data object, and will update every-time its data is updated.

> Attribute bindings ONLY update when their dependencies update. The framework is smart enough to observe data changes and detect which bindings care about them.

**`x-bind` for class attributes**

`x-bind` behaves a little differently when binding to the `class` attribute.

For classes, you pass in an object whose keys are class names, and values are boolean expressions to determine if those class names are applied or not.

For example:
`<div x-bind:class="{ 'hidden': foo }"></div>`

In this example, the "hidden" class will only be applied when the value of the `foo` data attribute is `true`.

**`x-bind` for boolean attributes**

`x-bind` supports boolean attributes in the same way as value attributes, using a variable as the condition or any JavaScript expression that resolves to `true` or `false`.

For example:
```html
<!-- Given: -->
<button x-bind:disabled="myVar">Click me</button>

<!-- When myVar == true: -->
<button disabled="disabled">Click me</button>

<!-- When myVar == false: -->
<button>Click me</button>
```

This will add or remove the `disabled` attribute when `myVar` is true or false respectively.

Boolean attributes are supported as per the [HTML specification](https://html.spec.whatwg.org/multipage/indices.html#attributes-3:boolean-attribute), for example `disabled`, `readonly`, `required`, `checked`, `hidden`, `selected`, `open`, etc.

> Note: If you need a false state to show for your attribute, such as `aria-*`, chain `.toString()` to the value while binding to the attribute. For example: `:aria-expanded="isOpen.toString()"` would persist whether  `isOpen` was `true` or `false`.

**`.camel` modifier**
**Example:** `<svg x-bind:view-box.camel="viewBox">`

The `camel` modifier will bind to the camel case equivalent of the attribute name. In the example above, the value of `viewBox` will be bound the `viewBox` attribute as opposed to the `view-box` attribute.