# Browser Caveats

A collection of things that stand out as edge-case problems and strange browser happenings.

## WFT

### …is iOS doing with fixed backgrounds?!

iOS devices (iPhone, iPad etc.) have issues with scaling background images that are fixed using `background-attachment: fixed`. The 'fixed' property is usually applied to a non-repeatable image and might possible have some sort of parralax feature to it.

It's an easy issue to find on Stack Overflow, but maybe use some sort of user-agent, class-based solution just for iOS. It's not ideal, but they're not playing ball and – at the end of the day – it's just an image.

```js
/* Somewhere in your script */
var b = document.documentElement;
b.setAttribute("data-useragent", Site.userAgent);
b.setAttribute("data-platform", Site.platform);
```

```scss
/* Assuming the background is applied to the 'body' element */
[data-useragent*="iPhone"] body {
	background-attachment: scroll;
	background-size: cover; // or 100%, depending on your needs
}
```

### …is Chome doing displaying my nice font so shit?!

Yeah, Chrome and Safari ahve that rendering issue thing with custom fonts. They should be crisp, but they're not. Now I'm not sure if Chrome moving over to the Blink engine will sort this problem out (for them) but generally speaking it's pretty crap at the time of writing this.

Every font throws up different issues, but here are some tips and tricks to play around with:

```scss
/* text-stroke can 'thicken' out light fonts and sometimes smooth things out */
-webkit-text-stroke: 0.5px #333;
```

SVG fonts sometimes render better on Webkit, but changing the `@font-face` order will keep you up at night. There's a quick fix using a media-query, which I've lost the link to where I originally found it.

```scss
@font-face {
	font-family: 'boomtime';
	src: url('includes/fonts/boomtime.eot');
	src: url('includes/fonts/boomtime.eot?#iefix') format('eot'),
	url('includes/fonts/boomtime.woff') format('woff'),
	url('includes/fonts/boomtime.ttf') format('truetype'),
	url('includes/fonts/boomtime.svg') format('svg');
	font-weight: normal;
	font-style: normal;
}

/* This might render a better font */
@media screen and (-webkit-min-device-pixel-ratio: 0) {
	@font-face {
		font-family: 'boomtime';
			src: url('fonts/chunk-webfont.svg') format('svg');
		}
	}
}
```

Lastly, there's always [`-webkit-font-smoothing`](http://css-tricks.com/beefing-up-dull-text-in-webkit/).
```scss
html, body {
    -webkit-font-smoothing: antialiased;
    font-smoothing: always;
}
```


## Interactions

### …with form input elements and zooming:
If the calculated font size of your input is less than 16px IOS devices will automatically zoom in on focus.

This only happens when you set the viewport to allow user scaling, which means you can zoom in and out.

A work around involves toggling the meta tag on focus, which is bad practice, but is can solve iOS issues, but raises issues on windows and android devices.

## Performance Issues

### …with fixed position elements:

[@Source](http://benfrain.com/improving-css-performance-fixed-position-elements/)

If you’re using fixed positioning elements on a page, ensure you add a property & value pair that will promote the element to its own layer (transform3d or backface-visibilty for example). This will prevent WebKit/Chrome re-painting it on scroll.

> When elements repaint, the dirty rectangle calculation is done per layer. So if an element is on its own layer then it won’t affect anything else. If you promote a fixed header – say – then when content appears at the bottom of the page there is only the new content that needs to be painted. Without the promotion the header needs to be repainted at the top of the page. You might wonder why we don’t automatically promote fixed position elements. The answer is: **we do for high DPI screens, but we don’t for low DPI** because we lose sub-pixel antialiasing on text, and that’s not something we want to by default. On high DPI screens you can’t tell, so it’s safe there.

> -- *<cite>[Paul Lewis](http://aerotwist.com/)</cite>*

