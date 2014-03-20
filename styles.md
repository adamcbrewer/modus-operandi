# CSS

## Be Neat, Professional and Responsible

* Four-space indentation.
* Remove unit specifiers with values of zero.
* Never use `id` selectors.
* Grouped selectors should be each be on their own line.
* Comma-separated values should include a space after each comma.
* Hex values should all be lowercase; shorthand where possible.
* [Obey the CSS Inception rule](http://thesassway.com/beginner/the-inception-rule): never go more than three levels deep.
* `px` font-sizes should always be avoided where possible; opt for `em` or preferably `rem`.
* Single value declarations can exist on a single line if needed.
* Use `%` units for layout styles that change (like left/right paddings), `ems` for elements which are sized relevant to their font size (like buttons) and `px` only when content/layout is static and does not change.

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
/* A SASS rem/em font-size mixin to help in assisting the above font-size declarations */
@mixin font-size($sizeValue: 1.4) {
    $remValue: $sizeValue;
    $pxValue: ($sizeValue * 10);
    font-size: #{$pxValue}px;
    font-size: #{$remValue}rem;
}
```


## Naming Conventions

Conventions are great, but being too over-specific and hard-arsed can really be difficult to work with and takes up more time than it's worth. Working quickly and efficiently is the main goal here, so the following only serves as a best-practices guide.

The extend of the BEM conventions totally depends on the size of the project and the number of developer involved. Larger projects need more rigid conventions whereas smaller ones usually don't run in to maintainability issues.

### Modules

Module names should be terse, non-representative of the content being styled and broken down into module, submodules, modifiers, and states. If a module name comprises of two words then remove the spacing (although camelCasing could also be a consideration [ala SuitCSS](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md)).

### Submodules

Use a single hyphen to write submodules. For example, `.module-submodule`. Pluralised modules such as `.tabs` can have submodules named `.tab` as an exception.

### Modifiers

Both modules and submodules can be modified with extender-classes, using double dashes to show the modification, e.g. `.module--modifier` and `.module-submodule--modifier`.

### States

Element states are prefixed appropriately, e.g. `.is-*` and can be declared on their own (`.is-visible`) or be entirely module dependant (`.is-favourite`). Examples: `is-active`, `is-loaded` and `is-open`.

Typically these states are a result of some sort of Javascript interaction.

### Context

It depends how complex the site is and how it functions, but adding a 'context' class [is new variation to me](https://github.com/suitcss). Contexts like `.has-content`, `.has-dropdown` and `.can-open` can be really expressive.


### Javascript Hooks
`.js-*` class names should **never** be delared anywhere in stylesheets (helps to maintain good code/style separation. Please refer to the [Javascript:hooks section](javascript.md#hooks--interactions) for more detail.

```html
<button class="btn btn--primary js-toggle"></button>
```

### Utilities
Low-level structure and composition. Utilities can be applied directly to any element within a component or exist on their own, such as `.u-pull-left` or `.u-inline-block`. I find utilities are only needed where designs contain a lot of unique styling situations.

### Using SASS
* Variables should prefixed and grouped according to their purpose/function.
* Modules and components should be separated from layout (site structure).
* Module declarations should always be included in your SASS import-sheet **after** layout declarations.
* Opting for mobile-first or employing responsive breakpoints desktop-down should – in my mind – follow the cascade. Saying this, I prefer to have these at the end of all my other styles.


```scss
/* _vars.scss */

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

```scss
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

### Rsponsive Styling

* **AVOID:** `px`, `width` & `height` on all declarations. These are reserved for components whose dimentions and positions are unaffected by resizing/screen-size.
* `max-width` should be the first port of call if a width declaration is required; height declarations are unnecessary 99% of the time if correct DOM flow is obeyed and the box-model is correctly understood.
* Always use `%` units for left & right paddings and margins on `block` elements and components.
* In addition to `%`, use `em` units for both `inline` and `inline-block` components.
* Component margins should follow [single directions declarations](http://csswizardry.com/2012/06/single-direction-margin-declarations/).

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

/* single direction margins. Use discretion where applicable. */
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
