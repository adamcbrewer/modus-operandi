# Responsive Design

## Thinking Responsively & Acting Responsibly

#### Making a website responsive and device agnostic is easy – the Web is inherently responsive and accessible. As designers and developers, we only have ourselves to blame for breaking sites.

An excerpt from [Jeff Veen's talk at SXSW c. 2004](http://veen.com/jeff/archives/000503.html) which I think is the most succinct description out there about what accessibility and responsivness actually means:

> I end up delivering solutions to my clients that are far less complex to implement, are much easier to maintain, cost exponentially less to serve, work on multiple browsers and devices, do way better in the search engine lottery, and — of course — are accessible to everyone … everyone … using the Web today. And try to argue with the business value of that.

> …

> And that’s why I don’t care about accessibility. Because when Web design is practiced as a craft, and not a consolation, accessibility comes for free.

I found that article through [Trent Walton's post on being "Device Agnostic"](http://trentwalton.com/) which he said very well.

> A responsive site may have flexible grids, fluid images, and media queries, but if it also scroll-hijacks desktop monitors while stutter-scrolling on touch devices, auto-loads heavy videos that break data plans, or asks users to rotate their screens 90° for the full immersive experience, I’d argue it’s not device-agnostic. Many sites, responsive or not, are built only with ideal scenarios and a small set of devices in mind.

> …

> I use the term device-agnostic, now synonymous (to me) with good web design, to distinguish those sites that embrace the inherent variability of the web—which, in itself, is nothing new.

…and so Jeff Veen entered my life. But Trent went on further to say:

> As web designers, it is our role to consider (and plan for) maximum reach and access, even when final results might seem underwhelming or less immersive.

> …

> With anything added to a page, you need to be able to answer the question of “What value does this provide?” and in turn be able to determine if the value outweighs the pain.

In closing: there is a difference between support and optimization.


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

