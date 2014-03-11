# Browser Caveats

A collection of things that stand out as edge-case problems and strange browser happenings.

## Performance Issues

### …with fixed position elements:

If you’re using fixed positioning elements on a page, ensure you add a property & value pair that will promote the element to its own layer (transform3d or backface-visibilty for example). This will prevent WebKit/Chrome re-painting it on scroll.

[Source](http://benfrain.com/improving-css-performance-fixed-position-elements/)

> When elements repaint, the dirty rectangle calculation is done per layer. So if an element is on its own layer then it won’t affect anything else. If you promote a fixed header – say – then when content appears at the bottom of the page there is only the new content that needs to be painted. Without the promotion the header needs to be repainted at the top of the page. You might wonder why we don’t automatically promote fixed position elements. The answer is: **we do for high DPI screens, but we don’t for low DPI** because we lose sub-pixel antialiasing on text, and that’s not something we want to by default. On high DPI screens you can’t tell, so it’s safe there.

> -- *<cite>[Paul Lewis](http://aerotwist.com/)</cite>*
