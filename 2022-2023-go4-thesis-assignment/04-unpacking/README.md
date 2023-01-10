# Unpacking 📦

Who, when, where and how is a website is accessed and consumed? 

A website can be thought as a space, a tool, a platform, a container, for accessing **content**. It works like an elastic, and flexes to accomodate its content. The *CSS* (Cascade Style Sheet) offers **directives** regarding visual appearance, which are not absolute obligations, but work in hand with the user's device and their browsing preferences ('dark mode' being a preference, as an example).

So, when it's on the web, you can't have the ultimate control on viewing contexts and your visitors: you need to embrace this 'flexibility' of contexts and display contexts. 

## Ressources toolbox (sections)

- [HTML tags and semantic HTML](#semantic-html-)
- [The CSS 'cascade'](#the-css-cascade)
- [CSS properties and values](#css-properties-and-values)
- [Designing and making the web across multiple devices](#designing-and-making-the-web-across-multiple-devices)
- [Footnotes](#footnotes)
- [Ressources](#ressources-)

## Semantic html ✅

> What are Semantic Elements? Semantic elements clearly **describe their meaning** through how the code is written.
> Examples of non-semantic HTML elements: `<div>` and `<span>` - Tell nothing about their content. 
> Examples of semantic elements: `<nav>`, `<header>`, `<form>`, `<table>`, and `<article>` - their content is clearly defined (you know what it is about without seeing it).

*Find more about semantic HTML*

> Read more on the [W3school](https://www.w3schools.com/html/html5_semantic_elements.asp)
  
- Cheat sheet 1: [Codecademy description of semantic elements](https://www.codecademy.com/learn/learn-html/modules/learn-semantic-html/cheatsheet)
- Cheat sheet 2: [MDN html cheatsheet](https://developer.mozilla.org/en-US/docs/Learn/HTML/Cheatsheet)
- Cheat sheet 3: [MDN html semantic blocks](https://developer.mozilla.org/en-US/docs/Glossary/Semantics#semantics_in_html)
  
*Why is it important?*

1. Folks using screen readers (accessibility helping devices) can access your website
2. You put chances on your side to be future-proof 🤞
3. Your website can be *indexed* by search engines, can be scraped by APIs and and is also readable through 'reading mode' on safari
4. It might look better when printed, exported to .pdf, or exported to other formats

### What could be a *semantic* structure in the context of the thesis-as-a-website assignment?

Use the `<figure>` tag for images / visual medias:
  
```
  <figure>
      <img src="path/to/your/image.jpg" alt="A painted representation of a forest with a big blue lake">
      <figcaption>Painting of a forest with a blue lake by Jane Doe</figcaption>
  </figure>
```

Put your footnotes in a `<footer>` tag if at the end of your document, in a `<aside>` tag is presented as a sidebar…<br>
Put your table of contents inside a `<nav>` tag.<br>
Put your thesis title inside the `<h1>` tag, the `<h1>` being inside the `<header>` tag, use the right tags for the right elements (`h1`, `h2`, […] `p`, `ul`, `ol`, `blockquote`, `a`, `sup`, etc)

## The CSS cascade

*Selectors, inheritance, specificity*

- [CSS specificity, and how it works](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
- [The 'cascade'](https://css-tricks.com/the-c-in-css-the-cascade/)
- [CSS 'inheritance'](https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance)
- [CSS selectors cheat list](https://www.w3schools.com/cssref/css_selectors.php)
- [CSS selectors almanach on *CSS Tricks*](https://css-tricks.com/almanac/selectors/)
- [The 'nth-of-type(x)' selector](https://css-tricks.com/almanac/selectors/n/nth-of-type/)

## CSS properties and values

Four main families of CSS properties

- Position and display properties
- Spacing, margin, padding properties (and the box model)
- Font, color, opacity, and other decorative properties
- Transition and transform properties

Read more:

- [CSS properties almanach on *CSS Tricks*](https://css-tricks.com/almanac/properties/)
- [More about the *box model*](https://css-tricks.com/the-css-box-model/)
- [Cool interactive demo of the *box model*](http://web.simmons.edu/~grovesd/comm244/notes/week6/box-layout-demo.html)

## CSS length units

CSS offers several different units for expressing dimensions. Many CSS properties take “length” values, such as width, margin, padding, font-size, etc. Length is a number followed by a length unit, such as 10px, 5%, etc. [Read more about css units](https://www.w3schools.com/css/css_units.asp), on the w3cschool.com.

*Relative* length units: specify a length relative to another length property, better for responsive uses.

Units (from w3schools.com):

- `em` - Relative to the font-size of the element (2em means 2 times the size of the current font)
- `ex` - Relative to the x-height of the current font (rarely used)
- `ch` - Relative to width of the "0" (zero)
- `rem` - Relative to font-size of the root element
- `vw` - Relative to 1% of the width of the viewport*
- `vh` - Relative to 1% of the height of the viewport*
- `vmin` - Relative to 1% of viewport's* smaller dimension
- `vmax` - Relative to 1% of viewport's* larger dimension
- `%` - Relative to the parent element

\* Viewport = the browser window size. If the viewport is 1200px wide, 1vw = 12px.

## CSS calc(), and min-max properties

`calc()` is a CSS function that allows defining value units as calculations of values. Calc accepts any value unit type (px, em, rem, %, vw, etc) and supports these operators: `+`, `-`, `*`, `/`. A great plus is that calc() accepts units of several types, so as an example it becomes possible to use relative units like percentage and subtract an absolute unit in pixels.

```
width: calc(100% - 20px);
width: calc(100vmax - 2rem);
width: calc( (100% / 6) - (1rem * 2) );
padding: calc(1rem * 0.75 );
font-size: calc(0.75rem + 2.5vw);
…
```

- [https://css-tricks.com/a-complete-guide-to-calc-in-css/](Read the complete guide on CSS Tricks)


***

## Designing and making the web across multiple devices

### Accessibility ♿

You can yourself make a test and press [Cmd]+[+], you'll likely zoom on the webpage (use [Cmd]+[-] for zooming out). This feature is actually used for folks with different viewing abilities that need it to see the content. Also: think about browser-activated 'dark' feature, text-to-speach devices, etc. There are dozens of thousands of possible combinations of browsers/versions + screen devices + interacting methods (hover/touch).

### Design, mobile-first 📱

When designing, think *mobile-first*. But what does that mean, exactly? Mobiles come in different sizes, different interacting method.

![... complicated](mobile-first.jpg)

Above examples are: a device with a square screen ratio, device with stylus, slow/small/low-res device (the 3310), smart watch, device with a trackball (!), foldable screen device (!!), tablet that is bigger than a desktop (!!!)... 🥴

This is why CSS media queries are for: https://css-tricks.com/a-complete-guide-to-css-media-queries/

#### Design for responsive/mobile ✏️

1. **Screen size** 320px for 'small' mobile devices (iPhone 5), 360-375px for 'average' and 400-420px for 'larger' devices. *If it works for 320px, it works for any devices.*
2. Most mobiles **can't reproduce 'hover'** interactions: there's no mouse. On the other hand, you can use 'touch' events if the way of interacting is to touch a screen. If you use 'hover' interactions to convey interactivity, think twice about another potential 'non-hover' visual cue.
3. The content is **likely to be displayed on a one column layout**. Space being scarce, you don't want a 'fixed' navigation element to take too much space on your layout. You can hide these in a element that expands (accordion-like, a sidebar, a hamburger menu...) or appear/dissapear based on scroll direction. Or you can choose to avoid menu elements and make sure your pages have a link to a 'next' content and a 'back to index' link...
5. **Think of the invisible structure of your website**, where every html tag is a division/box, from main container boxes to sub-containers, and then your content inside these boxes.
6. **Paper and pen can be useful!** Draw your website's structure on a piece of paper, this will help visualize what contains what.

##### Code, debug and test, for responsive/mobile 🛠️🔎

1. Use **CSS3 units** such as relative ems (rem), viewport units (`vw`, `vh`, `vmin`, `vmax`), and CSS variables: `--my-variable: myvalue;`.
2. The **`flexbox`** CSS property is super handy to set up a layout. You can easily change your order by changing the `flex` properties inside your `@media-queries` ! https://css-tricks.com/snippets/css/a-guide-to-flexbox/
3. Use the development tools to simulate your website at several screen sizes. On Google Chrome -> [Shift]+[Cmd]+[C] | on Firefox -> or [Alt]+[Cmd]+[I]. Then on both options you can find a mobile device / tablet icon that allows you to simulate several screen sizes.
4. But don't forget to also **test on a real mobile device** (for this you'll need to deploy your website online first, normally in a temporary/secret place but for this exercice you can push it online for testing purposes and implement further modifications afterwards on the same repository). Example of why test on a real device: *the 'rubber band' scrolling effect with [showing/hiding browser nav bar](https://www.google.com/search?q=ios+safari+navbar+scroll&source=lnms&tbm=isch) in iOS safari or [overscrolling issues](https://css-tricks.com/almanac/properties/o/overscroll-behavior/) from a modal to the page's body, or the way a css `vh` unit [is calculating differing on mobiles](https://dev.to/maciejtrzcinski/100vh-problem-with-ios-safari-3ge9), devices with a [notch](https://css-tricks.com/the-notch-and-css/) hiding content, etc.* Or **just the feeling of actually touching your website buttons/links** might make you realize they are too small/difficult to touch?

More tips about debugging on this Github's '[How-to-how](../3-how-to-how)' page.

## What about footnotes? 📖

See the ressource part of this Github's '[What about footnotes?](../5-footnotes)' page.

## Ressources 🧰

Features issues & support:

- **Can I use**..., support tables for HTML5, CSS3, etc: https://caniuse.com (❗)
- **CSS Tricks**'s *almanach, https://css-tricks.com/almanac/ (❗)
- **CSS Tricks**'s *A Complete Guide to...* series: https://css-tricks.com/guides/ (❗)
- **Stack overflow** (Q&A for developers, problem-sharing and fixing): https://stackoverflow.com/questions (❗)

Markup testing:

- **W3C validator markup** testing: https://validator.w3.org/ (free) (‼️)

Cross-device / screens testing:

- **Your browser's Developer tools** | Google Chrome -> [Shift]+[Cmd]+[C], or `View -> Developer Tools` | Firefox -> [Alt]+[Cmd]+[I], or `Tools -> Browser tools -> Web development tools` (‼️)
- **Browserstack** (test on multiple screens, but also browsers / user agents): https://www.browserstack.com/ (€)

Performance testing / audit:

- **Google Lighthouse**: https://developers.google.com/web/tools/lighthouse, use [Shift]+[Cmd]+[C] in *Google Chrome*, then access 'lighthouse' tab (❗)
- **Website Speed Test**: https://tools.pingdom.com/
- **Website Carbon Calculator**: https://www.websitecarbon.com/ (checks the CO2 emissions of your website)

Accessibility testing / audit:

- **WAVE** (website accessibility evaluation tool): https://wave.webaim.org (free) (❗)
- **WebAIM**: https://webaim.org/techniques/keyboard/ (free)
- **Web accessibility .com**: https://www.webaccessibility.com (free, €)
- **WebAIM** (contrast checker): https://webaim.org/resources/contrastchecker/

Social medias scrapers / debuggers:

- **Facebook sharing debugger tool**: https://developers.facebook.com/tools/debug/ (free)
- **Twitter cards validator tool**: https://cards-dev.twitter.com/validator (free)
- **LinkedIn post inspector**: https://www.linkedin.com/post-inspector (free)

Checklists:

- **The Front-end check-list** https://github.com/thedaviddias/Front-End-Checklist
- **A11y checklist**: https://www.a11yproject.com/checklist/
