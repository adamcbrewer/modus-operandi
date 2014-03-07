# CSS

## Universal Pricipals
* All lowercase.
* Four-space indentation.
* Remove unit specifiers with values of zero.
* grouped selectors should be each be on their own line.
* Comma-separated values should include a space after each comma.
* Hex values should all be lowercase; shorthand where possible.
* [Obey the CSS Inception rule](http://thesassway.com/beginner/the-inception-rule): never go more than three levels deep.
* `px` font-sizes should always be avoided where possible; opt for `em` or preferably `rem`.
* single value declarations can exist on a single line if needed.
* Declare styles with as weak/little specificity as possible and use the cascading effect within layouts and modules where needed.

Examples:
```scss
/* grouped selectors */
.btn,
.nav-link,
.action {
	border: 0;
	margin: 0; /* zero values have no units */
	/* ... */
}

/* Comma-separated values */
.overlay {
	background-color: rgba(0, 0, 0, 0.2);
	color: #f00;
}

/* single-line declaration */
.info { color: #ff0; }

/* em/rem font declarations. `body` font-size set to 62.5% */
.nav {
	font-size: 16px;
    font-size: 1.6rem;
}

/* A SASS rem/em font-size mixin */
@mixin font-size($sizeValue: 1.4) {
    $remValue: $sizeValue;
    $pxValue: ($sizeValue * 10);
    font-size: #{$pxValue}px;
    font-size: #{$remValue}rem;
}
```

## Responsive Styles
* **AVOID:** `px`, `width` & `height` on all declarations. These are reserved for components whose dimentions and positions are unaffected by resizing/screen-size.
* `max-width` should be the first port of call if a width declaration is required; height declarations are unnecessary 99% of the time if correct DOM flow is obeyed and the box-model is correctly understood.
* Always use `%` units for left & right paddings and margins on `block` elements and components.
* In addition to `%`, use `em` units for both `inline` and `inline-block` components.
* Component margins should follow [single directions declarations](http://csswizardry.com/2012/06/single-direction-margin-declarations/).

Examples:
```scss
/* percentage padding */
.wrapper {
	padding: 10px 4%; /* px OK here as typographic flow is unaffected */
}

/* em padding on inline elements - button size responds to font size. */
.btn {
	padding: 0.4em 1.2em;
	display: inline-block;
	font-size: 1.8rem;
}

/* single direction margins */
p { margin: 0 0 2.4em; }
h1,
h2,
h3 { margin: 0 0 1.4em; }

/* responsive, centered content box using max-width amd margins */
.box {
	max-width: 12em; /* can be px */
	margin: 0 auto 2em;
}

```

## SASS Specific
* Variables should prefixed and grouped according to their purpose/function.
* Modules and components should be separated from layout (site structure).
* Module declarations should always be included in your SASS import-sheet **after** layout declarations.

Examples:
```scss
/* Prefixed/grouped vars */
$c-primary: #f00;
$c-secondary: #00f;

$f-title: "Impact";
$f-body: "Georgia";
$ff: $f-body, Arial, sans-serif;

/* import-sheet order: main.scss */
@import "libs/mixins";
@import "libs/functions";
@import "fonts";
@import "vars";
@import "base";
@import "layout";
@import "modules";
@import "media";
```

## Structure and BEM Conventions
* Never use CamelCase.
* Module naming is terse and non-specific.
* Prefixed/grouped modules that share common traits are separated by a single dash.
* Extended modules require a double dash.

The extend of the BEM conventions totally depends on the size of the project and the number of developer involved. Larger projects need more rigid conventions whereas smaller ones usually don't run in to maintainability issues.

Examples:
```scss
/* module declaration */
.icon {
	display: block;
	margin: 0;
	font-family: $f-icons; /* using font-icons */
}

/* prefixed/grouped modules */
[class*="icon-"] {
	display: inline-block;
	color: #555;
}
.icon-star {
	font-size: 1.8rem;
}
.icon-home {
	&:hover {
		color: #000;
	}
}

/* ...or the modules can be nested in SASS */
.icon {
	background: transparent url(../img/sprite.png) no-repeat 0 0;
	display: inline-block;
	width: 24px;
	height: 24px;

	&.icon-star { background-position: 0 -24px; }
	&.icon-trash { background-position: 0 -48px; }
}

.btn {
	padding: 0.4em 1em;
	margin: 0;
	border: 1px solid #ddd;
	border-radius: 4px;
	color: #333;
	background-color: #fff;

	/* modifiers: double-dash */
	&.btn--primary {
		background-color: $c-primary;
	}

	/* sub-modules: single-dash */
	.btn-icon,
	.icon {
		display: inline-block;
		margin-right: 0.4em;
	}
}

```

## Javascript Hooks
JS hooks are prefixed with `.js-*` and **never** delared anywhere in the styles. This helps maintain good code/style separation. Additionally, the `id` in unique selections with optional `[data-*]` attributes (further explained in the Javascript section).

Example:
```html
<button class="btn btn--primary js-toggle"></button>
```

## Element/Component States
Element states are prefixed appropriately, e.g. `.is-*` and can be declared on their own (`.is-visible`) or be entirely module dependant (`.is-favourite`). Typically these states are a result of some sort of Javascript interaction.

## Utilities
Low-level structural, positional, and visual traits. Utilities can be applied directly to any element within a component.

## Media Queries
Opting for mobile-first or employing responsive breakpoints desktop-down should – in my mind – follow the cascade. Saying this, I prefer to have these at the end of all my other styles.

## Examples

```scss
/* _layout.scss */

/* Modifying a module as layout requires */
.header {
	.btn {
		border: 1px solid #bbb;
		border-radius: 4px;
	}
}

```

``` css
/* _modules.scss */

/* Utilities */
.u-pullright { /* … */ }
.u-text-left { /* … */ }
.u-block { /* … */ }

/* prefixed/grouped modules */
[class*="icon-"] {
	display: inline-block;
	color: #555;
}
.icon-star {
	font-size: 1.8rem;
}
.icon-home {
	&:hover {
		color: #000;
	}
}

/* Parent/layout modules & dependant modules */
.nav-list {

	&.is-expanded { /* … */ }

	.nav-item { /* … */ }
	/* cascading at work */
	.nav-link {
		color: #129793;
		display: inline-block;
	}
}

/* weak specificity, which is what we want to modify it later (above) */
.nav-link {
	color: #ff0000;
	text-decoration: none;

	&:hover,
	&.is-active {
		text-decoration: underline;
	}
}

/* we don't have to worry about overriding .nav-link anywhere else as this sub-nav acts as a parent/layout module containing its modifications */
.sub-nav {
	.nav-link {
		color: #ff634d;
	}
}

/* Typical modules */
.btn {
	padding: 0.4em 1em;
	margin: 0;
	border: 0;
	color: #333;
	background-color: #fff;

	/* modifiers first */
	&.btn--large {
		padding: 0.6em 1.2em;
	}

	&.btn--primary {
		background-color: $c-primary;
	}

	&.btn--alt,
	&.btn--special {
		font-family: $ff-serif;
	}

	/* nested elements */
	.icon-star {
		margin-right: 0.4em;
		color: inherit;
	}
}
```
