# Javascript

## Syntax

### The Single `var` Pattern
Pretty much all of my code has been written using the single declaration pattern, but having read [this article](http://danielhough.co.uk/blog/single-var-pattern-rant) by [@basicallydan](http://twitter.com/basicallydan) I hate to agree with him. I now try and use multiple vars where I can.

```js
/* Not so great, error-prone, but looks nice */
var foo = 'foo',
	bar = 'bar',
	baz;

/* Better for all reasons in the link above */
var foo = 'foo';
var bar = 'bar';
var baz;

```

### Hooks & Interactions

The `id` attribute and `.js-*` class names are reserved for any interaction required.

Purely interactive actions and triggers/toggles, `<button>` elements are used. Interactions that follow conventional links and that represent actual content then `<a>` tags are used.

`data-*` attributes are used for either action-specific data, and/or a group of target elements being triggered. If an action is tied to a specific element then `id` attributes should prefereably be used.

```html
<!-- HTML -->

<!-- the trigger -->
<button class="js-toggle" data-value="foo">Pump up this button</button>

<!-- the targeted element… -->
<article id="foo"><!-- … --></article>

<!-- …or a group of elements -->
<li data-group="foo"><!-- … --></li>
<li data-group="foo"><!-- … --></li>
<li data-group="foo"><!-- … --></li>
```
