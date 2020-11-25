---
doc: 'Alpine JS'
title: 'x-html'
slug: 'x-html'
order: 8
section: 'Directives'
section_order: 1
---

# `x-html`

Works similarly to `x-bind`, but will update the `innerHTML` of an element.

**Example:** 

```html
<span x-html="foo"></span>
```

**Structure:** 

```html
<span x-html="[expression]"
```

`x-html` works similarly to `x-bind`, except instead of updating the value of an attribute, it will update the `innerHTML` of an element.

> **Only use on trusted content and never on user-provided content.**

> Dynamically rendering HTML from third parties can easily lead to [XSS](https://developer.mozilla.org/en-US/docs/Glossary/Cross-site_scripting) vulnerabilities.