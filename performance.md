# Browser Performance

## Pay Particular Attention To:
+ Don't use data URIs as they're mega slow on mobile devices ([source](http://www.mobify.com/blog/data-uris-are-slow-on-mobile/)).

### CSS
All styles should be included as a single file, in the header, minified and compressed when deploying.

### Javascript
All Javascript files should be minified into a single file and, yes, placed at the bottom of the site. HTML5 `async` and `defer` attributes should not be used as a valid reason to put scripts in the header [reference needed]. Only feature detection and async scripts should live in the header.

The only case for using separate files would be in the case for progressive enhancement by using a feature detection library like [Modernizr](http://modernizr.com/).

All analytics & tracking scripts should be checked to ensure they load asynchronously.

## Images
All images should be optimised before deploying. A tool worth mentioning is [http://jamiemason.github.io/ImageOptim-CLI/](ImageOptim) by @jamiemason.

### GZIP Compression (Currently only PHP)
On apache, gzipping should be enabled throught the mod_deflate directive. Source files should have an `.htaccess` with the following as a minimum:

```bash
#
# Enable Gzip compression for all CSS and JS files, if the browser accepts them
#
<ifModule mod_deflate.c>
	<filesMatch "\.(js|css)$">
		SetOutputFilter DEFLATE
	</filesMatch>
</ifModule>
```

The [HTML5 Boilerplate](http://html5boilerplate.com/) should be consulted for futher information.
