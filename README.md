modus-operandi
==============
aka Method of operation.

This is a guide I use as a reference for my own development standards.

## Responsive Design

*todo*

## CSS

### Syntax

#### Universal
* Four-space tab indentation.
* Remove unit specifiers with values of zero.
* grouped selectors should be easch be on their own line.
* Comma-separated values should include a space after each comma.
* Hex values should all be lowercase; shorthand where possible.
* [Obey the CSS Inception rule](http://thesassway.com/beginner/the-inception-rule): never go more than three levels deep.
* Wield the cascade.
* `px` font-sizes should always be avoided where possible; opt for `em` or preferably `rem`.
* Declare styles with as weak/little specificity as possible and use the cascading effect within layouts and modules where needed.

#### SASS Specific
* Variables should prefixed and grouped according to their purpose/function.
* Modules (reusable components) should be separated from layout (site structure).
* Module declarations should always be included in your SASS import-sheet **after** layout declarations.

### Structure and BEM Conventions
* Module naming is terse and non-specific.
* Prefixed/grouped modules that share common traits are separated by a single dash.
* Extended modules require a double dash.

### Hooks & States
* JS hooks are prefixed with `.js-*` **never** delared anywhere in the styles. These are for javascript use only and to maintain a good code/style separation.
* Element states are prefixed appropriately, e.g. `.is-*`.
* States can be declared on their own (`.is-visible`) or exist entirely within a module (`.is-favourite`).

### Caveats
* Long class-names, prefixed/grouped classes and nested modules dependant on parent modules all use single dashes, but the complexity of the BEM structure can be adjusted on a per-project basis.

### Example

```css
/* _layout.scss */

/* Modifying a module as layout requires */
.header {
	.btn {
		border: 1px solid #bbb;
		border-radius: 4px;
	}
}

```

```css
/* _modules.scss */

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
	.nav-item {
		/* ... */
	}
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

## Javascript

*todo*

### HTML

*todo*

## Inspiration, References & Credit
[Coding standards front end - specialmoves.com](http://specialmoves.github.io/coding-standards-front-end/)
[Code-guide by @mdo](http://mdo.github.io/code-guide/)
[GitHub Style guides](https://github.com/styleguide)
[BBC - Mobile Accessibility Guidelines](http://www.bbc.co.uk/guidelines/futuremedia/accessibility/mobile/developers)
[Design and Development Standards by @snugug](https://github.com/Snugug/north#responsive-web-design)
