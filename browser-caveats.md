# Browser Caveats

A collection of things that stand out as edge-case problems and strange browser happenings.

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

