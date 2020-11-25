---
doc: 'Alpine JS'
title: 'Installation'
slug: 'installation'
order: 2
---

# Installation

## From CDN

Add the following script to the end of your `<head>` section.

```html
<script src="https://cdn.jsdelivr.net/gh/alpinejs/alpine@v2.x.x/dist/alpine.min.js" defer></script>
```

That's it. It will initialize itself.

For production environments, it's recommended to pin a specific version number in the link to avoid unexpected breakage from newer versions. For example, to use version `2.7.3` (latest):

```html
<script src="https://cdn.jsdelivr.net/gh/alpinejs/alpine@v2.7.3/dist/alpine.min.js" defer></script>
```

### IE11 Support

Use the following scripts instead for IE11 support.

```html
<script type="module" src="https://cdn.jsdelivr.net/gh/alpinejs/alpine@v2.x.x/dist/alpine.min.js"></script>
<script nomodule src="https://cdn.jsdelivr.net/gh/alpinejs/alpine@v2.x.x/dist/alpine-ie11.min.js" defer></script>
```

The pattern above is the [module/nomodule](https://philipwalton.com/articles/deploying-es2015-code-in-production-today/) pattern that will result in the modern bundle automatically loaded on modern browsers, and the IE11 bundle loaded automatically on IE11 and other legacy browsers.

## From NPM

Install the package from npm.

```
npm i alpinejs
```

Include it in your script.

```javascript
import 'alpinejs'
```