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
