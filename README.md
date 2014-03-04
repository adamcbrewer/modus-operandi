modus-operandi
==============
aka method of operation.

This is a guide I use as a reference for my own development standards.

## Responsive Design

*todo*

## CSS

### Universal
* All lowercase.
* Four-space indentation.
* Remove unit specifiers with values of zero.
* grouped selectors should be each be on their own line.
* Comma-separated values should include a space after each comma.
* Hex values should all be lowercase; shorthand where possible.
* [Obey the CSS Inception rule](http://thesassway.com/beginner/the-inception-rule): never go more than three levels deep.
* `px` font-sizes should always be avoided where possible; opt for `em` or preferably `rem`.
* Declare styles with as weak/little specificity as possible and use the cascading effect within layouts and modules where needed.

### Responsive Styles
* **AVOID:** `px`, `width` & `height` on all declarations. These are reserved for components whose dimentions and positions are unaffected by resizing/screen-size.
* `max-width` should be the first port of call if a width declaration is required; height declarations are unnecessary 99% of the time if correct DOM flow is obeyed and the box-model is correctly understood.
* Always use `%` units for left & right paddings and margins on `block` elements and components.
* In addition to `%`, use `em` units for both `inline` and `inline-block` components.
* Component margins should follow [single directions declarations](http://csswizardry.com/2012/06/single-direction-margin-declarations/).

### SASS Specific
* Variables should prefixed and grouped according to their purpose/function.
* Modules and components should be separated from layout (site structure).
* Module declarations should always be included in your SASS import-sheet **after** layout declarations.

### Structure and BEM Conventions
* Never use CamelCase.
* Module naming is terse and non-specific.
* Prefixed/grouped modules that share common traits are separated by a single dash.
* Extended modules require a double dash.

### Javascript Hooks
JS hooks are prefixed with `.js-*` and **never** delared anywhere in the styles. This helps maintain good code/style separation. Additionally, the `id` in unique selections with optional `[data-*]` attributes (further explained in the Javascript section).

Example:
```html
<button class="btn btn--primary js-toggle"></button>
```

### Element/Component States
Element states are prefixed appropriately, e.g. `.is-*` and can be declared on their own (`.is-visible`) or be entirely module dependant (`.is-favourite`). Typically these states are a result of some sort of Javascript interaction.

### Utilities
Low-level structural, positional, and visual traits. Utilities can be applied directly to any element within a component.

### Media Queries
Opting for mobile-first or employing responsive breakpoints desktop-down should – in my mind – follow the cascade. Saying this, I prefer to have these at the end of all my other styles.

### Examples

``` css
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

### Caveats
Long class-names, prefixed/grouped classes and nested modules dependant on parent modules all use single dashes, but the complexity of the BEM structure can be adjusted on a per-project basis ([reference](https://gist.github.com/necolas/1309546)).

## Javascript

*todo*

### HTML

*todo*

## Inspiration, References & Credit
* [Code-guide by @mdo](http://mdo.github.io/code-guide/)
* [SuitCSS](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md)
* [Coding standards front end - specialmoves.com](http://specialmoves.github.io/coding-standards-front-end/)
* [GitHub Style guides](https://github.com/styleguide)
* [BBC - Mobile Accessibility Guidelines](http://www.bbc.co.uk/guidelines/futuremedia/accessibility/mobile/developers)
* [Design and Development Standards by @snugug](https://github.com/Snugug/north#responsive-web-design)
