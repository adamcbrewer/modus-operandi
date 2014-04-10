# Javascript

## Syntax

### Name Spacing

Always name-space. Having access to the application components through a dedicated global creates a good base, making sure all URLs, detected features and applications settings are easily extended from, not to mention deploying to different environments.

#### The HTML Base

Firstly, a good base is required to get things started and to set up the name space. The `data-base-url` attribute should ideally be set somewhere in your environment-specific config. `.no-touch` and `.no-js` classes are used for feature detection and for progressive enhancement – more attributes can be added, ala [Modernizr](http://modernizr.com/), but usually only a select few are needed.

```html
<!-- HTML -->

<!doctype html>

<!-- JS and touch feature detection -->
<html class="no-js no-touch" lang="en">
</head>

	<!-- ... -->

</head>

<!-- base-url value from your config settings -->
<body data-base-url="http://yoursite.com">

	<!-- ... -->

</body>
</html>

```

#### The Javascript

```js
/* script.js */

// Anonymous wrapper. Third party libraries should also be
// referenced here if being used. `undefined` always comes last :).
;(function(window, document, undefined){

	/**
	 * Name-spacing
	 *
	 * Define which objects belong in the global object.
	 *
	 */
	window.Site = {
		basePath: document.body.getAttribute('data-base-url'), // from our HTML example above
		userAgent: navigator.userAgent,
		platform: navigator.platform
	};

	// the rest of your code
	/* ... */

}(window, document));

```

### Coding Conventions

#### Human-Readable

At the risk of being overly verbose, this actually reduces the need for comments and code explanations. From experience, it flows really nicely and is a lot easier to grasp at first glance, especially when returning to old code.

```js
var doublePageFunctionalityEnabled = this.$pageImages.length === 2;
if (doublePageFunctionalityEnabled) {
    // code
}
```

#### The Single `var` Pattern
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

#### Hooks & Interactions

The `id` attribute and `.js-*` class names are reserved for any interaction required.

Purely interactive actions and triggers/toggles, `<button>` elements are used. Interactions that follow conventional links and that represent actual content then `<a>` tags are used.

`data-*` attributes are used for either action-specific data, and/or a group of target elements being triggered. If an action is tied to a specific element then `id` attributes should prefereably be used.

```html
<!-- HTML -->

<!-- the trigger -->
<button class="js-toggle" data-value="foo">Pump up this button</button>

<!-- the targeted element… -->
<article id="foo"><!-- ... --></article>

<!-- …or a group of elements -->
<li data-group="foo"><!-- ... --></li>
<li data-group="foo"><!-- ... --></li>
<li data-group="foo"><!-- ... --></li>
```
