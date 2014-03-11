# Responsive Design

## Thinking Responsively & Acting Responsibly

*todo*

## Grids and layout

For fluid grids (expanding & contracting) keep all widths and gutters in percentages. Gutters, paddings and spacings can be in `px`, but this can affect 'breaks' in layout where fluid percentages are used, so discretion is advised.

**Avoid** hard-set widths and fixed-sized/min-sized gutters, such as galleries where the images have a minimum width/height. This is difficult to keep responsive without Javascript and it also means you have to set media query breakpoints each time you drop a column, i.e. if the columns are 320px wide you're going to have to specify at least 6-9 breakpoints.

Both depend on the style & design. Pick your starting point and adjust bigger or smaller viewports from there.

## Useful Links & Resources

### Required Reading & Watching
+ [John Allsop: A Dao of Web Design (April 07, 2000)](http://alistapart.com/article/dao/).
+ [Jeremy Keith talking about "unknown unknowns"](http://vimeo.com/50745034).

### Regarding Page-weight
+ [Media Query Asset Downloading Results](http://timkadlec.com/2012/04/media-query-asset-downloading-results/).

### Responsive Patterns and Navigation Examples
+ [Responsive patterns: A comprehensive list by Brad Frost for all situations](http://bradfrost.github.io/this-is-responsive/patterns.html).
+ [Navigation patterns from Brad Frost: pros and cons](http://bradfrostweb.com/blog/web/complex-navigation-patterns-for-responsive-design/).
+ [Navigation examples from Tympanus](http://tympanus.net/Development/SidebarTransitions/).
+ [Another write-up of responsive navigation demos and thoughts](http://responsivenavigation.net/). [Best example here](http://responsivenavigation.net/examples/multi-toggle/).
+ Viewport-meta tag From Quirksmode: [the directives](http://www.quirksmode.org/mobile/metaviewport#link2), [tests](http://www.quirksmode.org/mobile/metaviewport#link8) & [browser bugs](http://www.quirksmode.org/mobile/metaviewport#link19).

