# Responsive Design

## Thoughts

#### On responsive design everywhere…

Responsive design is something I deal with daily and is a consideration in everything I build. When the term first became popular it became a personal goal to be as well-informed as possible, and to rethink as well as refactor everything that was once thought of as ‘the way’ of doing things.

In my opinion, developers shouldn’t make responsive design a feature – knowing how to work responsively should be ingrained in what we do as it affects the usability and accessibility of everything. Not thinking responsively can inhibit how the content – the main focus of any site – is delivered.

I’ve built both small-mid scale sites and a few large-scale applications. Many have their own responsive considerations, such as maps, carousels, modals (pop-ups), etc. so to build a responsive site takes a broad knowledge of how common features are used.

#### On implementing a responsive approach…

More often than not the biggest consideration is usually navigation – it’s generally the most used part of the site. Too many effects can lead to a bad experience, but "clear, quick, and easy-to-use" means your site’s accessibility could improve ten-fold.

Another consideration is the content hierarchy, which is over-thought a helluva lot. How the page is built from the start determines how easy and how robust a responsive implementation would be, but it does require a sound knowledge of basic CSS box-model concepts of which too many developers overlook as trivial.

Spending too much time predefining breakpoints in a design and catering for specific devices leads to a biased output and not a true responsive implementation, or flow.

#### On the process of a project…

The most typical process I’ve experienced is a design get’s signed off for first, which includes layouts for a large screen and one or two other smaller-screen layouts – these are usually for iPads and iPhones, using dimensions perceived to be ‘most popular.’ A developer is then called in and has to make the layout and features work.

The majority of us are relatively inexperienced with responsive design as it’s still a new concept, but it still surprising to me how little the developer is brought in on the initial stages. Someone with decent technical experience in building responsive design is absolutely needed before any crucial decisions are made and work is approved and started.

#### On designing in the browser…

I normally get a sense from the mock-ups and design of how I’m going to approach the build, but there’s no substitute for the browser. I’ll work on the base, but the large-to-small nuances, breakpoints and usability features (touch interactions as opposed to hovers, etc.) I’ll produce just by having a play around and experimenting.


#### On and building by concept…
I feel it’s best to know how a page is going to work inside and out before anything is agreed design-wise. Once everything is considered and nothing is flagged as a likely usability issue then the first line of code get’s written. Mental notes are kept on how to address the fluidity and content hierarchy stacking order.

#### On prototyping…

I’ll build prototypes only if working to an iterative process or if the budget allows, but generally it’s a case of ‘this is how I think it’ll work’ and then just go for it. Responsive design is actually very easy, it’s only the functionality and special, creative features that complicate things. If I know enough of the project and don’t see any major problem areas then prototypes aren’t needed as there’s very little to worry about.

## Words from Others

Making a website responsive and device agnostic is easy – the Web is inherently responsive and accessible. As designers and developers, we only have ourselves to blame for breaking sites.

Everyone has their say of what Responsive Design is, but the following excerpts are just a few I 100% agree with, as well as from people I respect in the industry.

### [Jeff Veen](http://veen.com)

An excerpt [SXSW c. 2004](http://veen.com/jeff/archives/000503.html) which I think is the most succinct description out there about what accessibility and responsivness actually means:

> I end up delivering solutions to my clients that are far less complex to implement, are much easier to maintain, cost exponentially less to serve, work on multiple browsers and devices, do way better in the search engine lottery, and — of course — are accessible to everyone … everyone … using the Web today. And try to argue with the business value of that.

> …

> And that’s why I don’t care about accessibility. Because when Web design is practiced as a craft, and not a consolation, accessibility comes for free.

### [Trent Walton](http://trentwalton.com)

From his post on being [Device Agnostic](trentwalton.com/2014/03/10/device-agnostic/):

> A responsive site may have flexible grids, fluid images, and media queries, but if it also scroll-hijacks desktop monitors while stutter-scrolling on touch devices, auto-loads heavy videos that break data plans, or asks users to rotate their screens 90° for the full immersive experience, I’d argue it’s not device-agnostic. Many sites, responsive or not, are built only with ideal scenarios and a small set of devices in mind.

> …

> I use the term device-agnostic, now synonymous (to me) with good web design, to distinguish those sites that embrace the inherent variability of the web—which, in itself, is nothing new.

> …

> As web designers, it is our role to consider (and plan for) maximum reach and access, even when final results might seem underwhelming or less immersive.

> …

> With anything added to a page, you need to be able to answer the question of “What value does this provide?” and in turn be able to determine if the value outweighs the pain.

### [Harry Roberts](http://csswizardry.com)

When asked ["What is the one thing with responsive web design you would like to see improved?"](http://responsivedesignweekly.com/interview/responsive-interview-harry-roberts/):

> General knowledge of its implications: how much responsive design impacts responsive development (e.g. a designer saying ‘this is large screen, this is small’ is very different to actually working out how to tie those ribbons together), how much it (can) affect(s) performance, how much remains unknown (small-screen does not equal slow connection, retina capable does not mean retina is always suitable, etc.). RWD is still in its infancy, but I think we all need to slow it down a bit, be prudent, be cautious, and be aware. RWD is great, really great, but it brings a lot of implications with it.


## Grids and layout

For fluid grids (expanding & contracting) keep all widths and gutters in percentages. Gutters, paddings and spacings can be in `px`, but this can affect 'breaks' in layout where fluid percentages are used, so discretion is advised.

**Avoid** hard-set widths and fixed-sized/min-sized gutters, such as galleries where the images have a minimum width/height. This is difficult to keep responsive without Javascript and it also means you have to set media query breakpoints each time you drop a column, i.e. if the columns are 320px wide you're going to have to specify at least 6-9 breakpoints.

Both depend on the style & design. Pick your starting point and adjust bigger or smaller viewports from there.

## Useful Links & Resources

### Required Reading & Watching
+ [A collaborative resource and excellent source](https://github.com/Snugug/north#responsive-web-design)
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

