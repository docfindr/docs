---
doc: 'Alpine JS'
title: 'x-model'
slug: 'x-model'
order: 6
section: 'Directives'
section_order: 1
---

# `x-model`

Adds "two-way data binding" to an element. Keeps input element in sync with component data.

**Example:** 

```html
<input type="text" x-model="foo" />
```

**Structure:** 

```html
<input type="text" x-model="[data item]" />
```

`x-model` adds "two-way data binding" to an element. In other words, the value of the input element will be kept in sync with the value of the data item of the component.

> `x-model` is smart enough to detect changes on text inputs, checkboxes, radio buttons, textareas, selects, and multiple selects. It should behave [how Vue would](https://vuejs.org/v2/guide/forms.html) in those scenarios.

## `.number` modifier

**Example:** 

```html
<input x-model.number="age" />
```

The `number` modifier will convert the input's value to a number. If the value cannot be parsed as a valid number, the original value is returned.

## `.debounce` modifier

**Example:** 

```html
<input x-model.debounce="search" />
```

The `debounce` modifier allows you to add a "debounce" to a value update. In other words, the event handler will NOT run until a certain amount of time has elapsed since the last event that fired. When the handler is ready to be called, the last handler call will execute.

The default debounce "wait" time is 250 milliseconds.

If you wish to customize this, you can specifiy a custom wait time like so:

```html
<input x-model.debounce.750="search" />
<input x-model.debounce.750ms="search" />
```