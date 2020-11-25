---
doc: 'Alpine JS'
title: 'x-on'
slug: 'x-on'
order: 5
section: 'Directives'
section_order: 1
---

# `x-on`

Attaches an event listener to the element. Executes JS expression when emitted.

> You are free to use the shorter "@" syntax: `@click="..."`.

**Example:** 

```html
<button x-on:click="foo = 'bar'"></button>
```

**Structure:** 

```html
<button x-on:[event]="[expression]"></button>
```

`x-on` attaches an event listener to the element it's declared on. When that event is emitted, the JavaScript expression set as its value is executed. You can use `x-on` with any event available for the element you're adding the directive on, for a full list of events, see [the Event reference on MDN](https://developer.mozilla.org/en-US/docs/Web/Events) for a list of possible values.

If any data is modified in the expression, other element attributes "bound" to this data, will be updated.

> You can also specify a JavaScript function name.

**Example:** 

```html
<button x-on:click="myFunction"></button>
```

This is equivalent to: `<button x-on:click="myFunction($event)"></button>`

## `keydown` modifiers

**Example:** 

```html
<input type="text" x-on:keydown.escape="open = false" />
```

You can specify specific keys to listen for using keydown modifiers appended to the `x-on:keydown` directive. Note that the modifiers are kebab-cased versions of `Event.key` values.

Examples: `enter`, `escape`, `arrow-up`, `arrow-down`

> You can also listen for system-modifier key combinations like: `x-on:keydown.cmd.enter="foo"`

## `.away` modifier

**Example:** 

```html
<div x-on:click.away="showModal = false"></div>
```

When the `.away` modifier is present, the event handler will only be executed when the event originates from a source other than itself, or its children.

This is useful for hiding dropdowns and modals when a user clicks away from them.

## `.prevent` modifier

**Example:** 

```html
<input type="checkbox" x-on:click.prevent />
```

Adding `.prevent` to an event listener will call `preventDefault` on the triggered event. In the above example, this means the checkbox wouldn't actually get checked when a user clicks on it.

## `.stop` modifier

**Example:** 

```html
<div x-on:click="foo = 'bar'">
    <button x-on:click.stop></button>
</div>
```

Adding `.stop` to an event listener will call `stopPropagation` on the triggered event. In the above example, this means the "click" event won't bubble from the button to the outer `<div>`. Or in other words, when a user clicks the button, `foo` won't be set to `'bar'`.

## `.self` modifier

**Example:** 

```html
<div x-on:click.self="foo = 'bar'">
    <button></button>
</div>
```

Adding `.self` to an event listener will only trigger the handler if the `$event.target` is the element itself. In the above example, this means the "click" event that bubbles from the button to the outer `<div>` will **not** run the handler.

## `.window` modifier

**Example:** 

```html
<div x-on:resize.window="isOpen = window.outerWidth > 768 ? false : open"></div>
```

Adding `.window` to an event listener will install the listener on the global window object instead of the DOM node on which it is declared. This is useful for when you want to modify component state when something changes with the window, like the resize event. In this example, when the window grows larger than 768 pixels wide, we will close the modal/dropdown, otherwise maintain the same state.

> You can also use the `.document` modifier to attach listeners to `document` instead of `window`

## `.once` modifier

**Example:** 

```html
<button x-on:mouseenter.once="fetchSomething()"></button>
```

Adding the `.once` modifier to an event listener will ensure that the listener will only be handled once. This is useful for things you only want to do once, like fetching HTML partials and such.

## `.passive` modifier

**Example:** 

```html
<button x-on:mousedown.passive="interactive = true"></button>
```

Adding the `.passive` modifier to an event listener will make the listener a passive one, which means `preventDefault()` will not work on any events being processed, this can help, for example with scroll performance on touch devices.

## `.debounce` modifier

**Example:** 

```html
<input x-on:input.debounce="fetchSomething()" />
```

The `debounce` modifier allows you to "debounce" an event handler. In other words, the event handler will NOT run until a certain amount of time has elapsed since the last event that fired. When the handler is ready to be called, the last handler call will execute.

The default debounce "wait" time is 250 milliseconds.

If you wish to customize this, you can specify a custom wait time like so:

```
<input x-on:input.debounce.750="fetchSomething()">
<input x-on:input.debounce.750ms="fetchSomething()">
```

## `.camel` modifier

**Example:** 

```html
<input x-on:event-name.camel="doSomething()" />
```

The `camel` modifier will attach an event listener for the camel case equivalent event name. In the example above, the expression will be evaluated when the `eventName` event is fired on the element.