# Accessibility

##What is Web Accessibility?

Web accessibility is the inclusive practice of making your website
usable by people with all abilities and disabilities, allowing equal
access to all content and functionality.  This means can they
**perceive**, **understand**, **navigate** and **interact**with it.  

##Why Web Accessibility?

Around a third of disabled people experience difficulties related to
their impairment in accessing public, commercial and leisure goods and
services. As content authors who strive to be leaders in our industry it
is our social responsibility to create software that is as inclusive,
and as non-discriminatory as possible. Furthermore there are financial
and usability benefits of making products and services accessible to a
larger consumer base. 

###Web accessibility and the Law

In 2012 the Equality Act came into effect and replaced the Disability
Discrimination Act 1995 making it illegal to discriminate against people
with disabilities. 

The Code of Practice: Rights of Access - Goods, Facilities, Services and
Premises document published by the government's Equality and Human
Rights Commission to accompany the Act does refer explicitly to websites
as one of the "services to the public" it should be considered covered
by the Act, as it applies to anyone providing a service; public, private
and voluntary sectors. 

To date few companies have faced legal action over website
accessibility, but if overlooked the potential to be sued for
discrimination is there.

##Web Accessibility Considerations

For many, web accessibility is simply catering for the blind; this is a
short-sighted view. In Great Britain, there are over eleven million
people with a limiting long-term illness, impairment or disability the
most commonly reported impairments are those that affect mobility,
lifting or carrying. 

The prevalence of disability rises with age with around 6% of children
being disabled, compared to 16% of working age adults and 45% of adults
over State Pension age in Great Britain. These disabilities can be
classed as visual impairments, hearing impairments, mobility
impairments, cognitive disabilities and seizures. Thus it is our
prerogative to approach our application development with this in mind.

##Tackling Web Accessibility 

Whilst the application of web accessibility is subjective and
conditional to the product there are clear goals that need to be met. An
accessible website needs to be four things, **perceivable**,
**operable**, **understandable** and **robust**.  

###Perceivable:

*A user should know how to use the website.*

We need to provide text alternatives or captions for non-text content
such as images, video or audio. Content must be created so that it can
be read out of context, or presented in different ways such as semantic
headings or links to content. 

###Operable

*A user should be able to use the website.*

We cannot rely on users to only use a mouse, it must be keyboard
accessible or traversable using other software. We have to give users
enough time to digest and interact with the content and assist them in
navigating the application or site. 

###Understandable

*A user should be able to grasp the information presented to them*

Text should be readable and should operate in predictable ways by
following patterns such as content ordering using semantic markup.  We
must also help users to avoid and correct mistakes.

###Robust

*The site should adhere to standard development practices*

We must try to future proof the website or application as much as
possible allowing it to be flexible with future technologies.

##Addressing Impairments

An accessible website is a mixture of the above, the user experience and
visual design but how do we address individual impairments?

###Visual Impairments

**Problem**: Blindness, low vision, colour-blindness, some of which could
be caused by medical conditions or birth defects that cannot be
corrected with glasses. 

**Solution**: This can be tackled by allowing zooming or utilizing
colour contrast effectively.

###Hearing Impairments

**Problem**: deafness or hard-of-hearing, which cannot be aided with
assistive technologies such as hearing aids. 

**Solution**: we should not rely on audio cues, and we should provide
transcripts for audio and video media.

###Mobility Impairments

**Problem**: The inability to use a mouse, slow response time, limited
fine motor control that could be caused by muscular dystrophy, carpal
tunnel syndrome or neurological conditions due to accidents. 

**Solution**: allow the application to be navigable using a keyboard or
other assistive technology such as speech recognition software.

###Cognitive Disabilities:

**Problem**: Such as learning disabilities, distractibility, inability
to remember or focus on large amounts of information which could be
brought on by various types of depression, or behavioural disorders.  

**Solution**: Give the user plenty of time to interact with the content,
and help them avoid mistakes with appropriate dialogs and warnings.

###Seizures:

**Problem**: Photoepileptic seizures caused by visual strobe or flashing
effects.

**Solution**: Avoid flashing images and anything that flashes more than
three times in any one second period and checked against the Guidance
Note for Licensees on Flashing Images and Regular Patterns in
Television.

###Assistive technologies

There are a number of technologies that are available that aid disabled
(and abled) users to navigate the Internet. Some operating systems and
mobile devices have inbuilt accessibility features, such as screen
readers or contrast settings to aid the user.  There is also vast list
of other assistive software and hardware that needs to be taken into
consideration such as:
- Speech recognition
- Eye tracking
- Electronic pointing devices
- Sip-and-puff
- Wands and sticks
- Joysticks
- Trackballs
- Touch screens
- Braille displays
- Braille embossers

##Development Accessibility Standards

Developing an accessible website is not difficult. It requires basic
development skills, an understanding of the component you are developing
in correlation with the standard Web Content Accessibility Guidelines
(WCAG) and the Web Accessibility Initiative - Accessible Rich Internet
Applications (WAI-ARIA) roles.

###Web Content Accessibility Guidelines 

The WCAG is developed through the W3C process in cooperation with
individuals and organizations around the world, with a goal of proving a
single shared standard for web content accessibility that meets the
needs of individuals, organizations, and governments internationally.  

WCAG 2.0 is a stable, referenceable technical standard that has 12
guidelines that are organized under the 4 principles mentioned earlier:
**perceivable**, **operable**, **understandable**, and **robust**. For
each guideline, there are testable success criteria, which meet three
levels: **A**, **AA**, and **AAA**.  With **A**having the simplest and
**AAA**having the greatest accessibility considerations.

###Web Accessibility Initiative - Accessible Rich Internet Applications

WAI-ARIA is a technical specification published by the World Wide Web
Consortium that specifies how to increase the accessibility of web
pages, in particular, dynamic content and user interface components
developed with Ajax, HTML, JavaScript and related technologies. 

WAI-ARIA works by attaching meta information to HTML elements to convey
better understanding of how a component works or what it’s application
is on the page.

###In practice

There is a common belief in the industry that high levels of
accessibility are is impossible with rich interaction and innovative
look and feel. This is not necessarily the case as by combining the
WCAG, with WAI-ARIA and other techniques you can achieve something that
is truly rich in features but also accessible to users who require
assistive technology. However there are cases when, a **AA** standard
cannot be met.

##Cost of Accessibility 

Whilst additional development and testing is required, the cost of
developing an accessible website from the beginning is almost the same
as developing an inaccessible website. Redeveloping or retrofitting an
inaccessible website requires re-visiting old code and retesting almost
everything which obviously has an expensive overhead.

In order to truly determine the cost of accessibility we need to work
out the following: 

###Determining accessibility requirements

By adopting an agile approach we can develop in small chunks that allow
us to document and structure our code in a way that allows us to tackle
our highest impact components first.

###Developing internal style guides and best practices

By outlining standards taken from existing resources, documentation and
communities we can create a methodology of working that takes
accessibility into account from the beginning.  This allows for the
habits of the developers to be inclusive of the accessibility
requirements.  Furthermore the agile approach allows us to be flexible
with our style guides and practices.

###Training staff

Lack of accessibility understanding is not malicious but more a point of
education where there is ignorance. Once properly trained developers can
develop with a better idea of how to approach components, testers know
what to look for and end users receive a better product.

###Finding new toolsets

There are a multitude of existing tools and assistive technologies that
are available for testing and emulation, including automated testing
tools.

###Additional QA time & resources

Continuous testing and QA for accessibility is absolutely vital.
Specific requirements will need to be tackled on an adhoc basis based on
the problems outlined earlier in this document. Rules for testing should
be documented in a central resource such as a Confluence instance and
followed.  

The development team should also incorporate accessibility quality
assurance into their workflow and it should be part of their peer review
process to raise any potential accessibility issues that may have been
overlooked. 

However QA teams are more likely to discover accessibility failures due
to their typically non-developer nature but because accessibility is a
subjective subject it is possible for potential issues to be missed. QA
& development teams will require some degree of training. 

###Consultant Fees/Salary for an internal Subject Matter Expert

There are a few consultancies that offer training and expert analysis on
the subject of accessibility. It is a recommendation that some budget
should be allocated for consultation and/or training.

##Recommendation

It is recommended that we aim for a WCAG 2.0 AA standard of
accessibility whilst incorporating the usage of WAI-ARIA roles. Where
applicable, and in certain circumstances, the level of accessibility
will fluctuate between **A**an **AAA** to achieve the best user
experience. 

Furthermore a standardized approach to development is documented during
the build process.  Development teams take into account potential
accessibility issues and QA teams integrate this as part of their
testing routine alongside automated testing software. 

It’s also a recommendation that an accessibility statement be added to
the application or website to inform users of the methods undertaken to
improve the users perception of their experience. 

##References

####General Principles
 - http://webaim.org/intro/
 - http://ec.europa.eu/ipg/standards/accessibility/index\_en.htm
 - http://www.netxtra.net/insights/why-all-websites-should-be-accessible/
 - http://www.nomensa.com/blog/2012/7-web-accessibility-myths-2/
 - http://www.karlgroves.com/2011/11/30/how-expensive-is-accessibility/

####BBC accessibility guidelines
 - http://www.bbc.co.uk/accessibility/guides/

W3C Web Accessibility Initiative
 - http://www.w3.org/WAI/intro/accessibility.php
 - http://www.w3.org/WAI/WCAG20/glance/Overview.html
 - http://www.w3.org/WAI/intro/aria

####WebAim WCAG checklist
 - http://webaim.org/standards/wcag/checklist

####W3C ARIA Roles
 - http://www.w3.org/WAI/intro/aria
 - http://www.w3.org/TR/wai-aria/

####Mozilla foundation
 - https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA

####Assistive Technologies
 - http://webaim.org/articles/motor/assistive
 - http://www.mayer-johnson.com/category/assistive-technology

####Government and educational insitutions
 - http://webaccessibility.jhu.edu/what-is-accessibility/important.html

####Law & Compliance
 - http://www.seqlegal.com/blog/website-accessibility-and-equality-act-2010
 - http://www.rnib.org.uk/professionals/services/equalityact/pages/equality\_act\_compliance.aspx
 - http://www.legislation.gov.uk/ukpga/2010/15/part/3
 	- http://www.legislation.gov.uk/ukpga/2010/15/section/20
 	- http://www.legislation.gov.uk/ukpga/2010/15/section/21
 	- http://www.legislation.gov.uk/ukpga/2010/15/section/29
 - http://www.thirdsector.co.uk/news/619671/?DCMP=ILC-SEARCH
 - http://www.theregister.co.uk/2007/01/25/computer\_based\_exam\_discriminated\_against\_blind\_candidate/
 - http://www.w3.org/WAI/bcase/pol.html
 - http://www.w3.org/WAI/bcase/socog-case-study

####Disability Statistics
 - http://odi.dwp.gov.uk/disability-statistics-and-research/index.php

####Tools
 - http://www.w3.org/WAI/ER/tools/complete
 - http://www.microsoft.com/enable/at/types.aspx

