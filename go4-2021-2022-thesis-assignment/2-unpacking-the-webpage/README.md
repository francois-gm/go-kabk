# Unpacking the webpage

Who / when / where / how a website is accessed / consumed…
A website is a tool/platform/container for accessing content, and CSS offers **directions** regarding appearance (**not obligations**).

## *Good website* criteria (from a purely technical standpoint)

- Ressources loads fast (under 300ms) or are splitted to avoid excessive load times
- Interaction elements are properly timed ([300ms, no endless transitions](https://ux.stackexchange.com/questions/66604/optimal-duration-for-animating-transitions ))
- Coherent, semantic, and acknowledge expectable design patterns.
- Suggests the website structure/hierarchy in the design (breadcrumbs, menu as sitemap, table of contents). Where am I?
- Avoid interfering with native/expected browser behaviors and user preferences (scrolling functionalities, light/dark modes, cursor suggesting an element can be clicked, etc). 
- Looks **good** on any devices, screen sizes, interaction methods: [60% users on mobile devices](https://gs.statcounter.com/platform-market-share/desktop-mobile-tablet) (1 column, menu shortcuts, touch event), 40% on desktop (1 or multi-column, extended menu, mouse hover), phablets, foldable phones, mega-big ipads, etc…
- Agnostic of language directions (left-to-right, right-to-left) (more on [Material Design](https://material.io/design/usability/bidirectionality.html#mirroring-layout))
- Is understandable / accessible without CSS (uses appropriate html tags and page structure). Can be navigated with ‘tabs’ / focus, and screen readers (visual impairments, hearing impairment, etc).
- Takes into account a ‘performance’ budget for client-side features / properties that are resource-intensive (animating a css ‘filter’ blur property can be very demanding).

Sharing of resources / help regarding points up

### Ressources optimization

- Use .jpg for images, avoid .png over 500kb (and use only for transparency or if file is smaller than .jpg), avoid .gif over 500kb (and use only for moving or if smaller than .jpg).
- Consider using .svg files (yes!) instead of .png files
- Compress your .jpg with Photoshop using the 'Save for Web (Legacy)' option (under File->Export), [Shift]+[Alt]+[Cmd]+[s], with the appropriate image width resizing and the quality setting at **60** or below.
- If 'Save for Web (Legacy)' is not available, use 'Export As' (under File->Export).
- Your images should not be too big in relationship with the space they occupy. Consider capping images at **2400px** width for full screen width images, **1200px** for 50% screen width, and **900px** for 33% screen width.
- If you use the html `<video>` tag, export your video to .mp4 -> https://cloudconvert.com/mp4-converter and adjust the quality so you are at under 2mb per minute.
- Same applies with the `<audio>` tag, use .mp3 -> https://online-audio-converter.com and adjust so you're under 1mb / minute.
- If your media file is verrrrrrrrrrrrry heavy, consider using Vimeo, YouTube or Soundcloud and embed it on your website using the provided embed code. Some of these services provide an API to control play/pause, volume, etc, through Javascript.
- If your page is really image-heavy, consider implementing your images with a lazyload: https://afarkas.github.io/lazysizes/index.html
- Use a CDN (Content Delivery Network) to deliver your media files: https://cloudinary.com/ (cloudinary has a free tier, [Documentation](https://cloudinary.com/documentation/image_optimization)). Imagekit.io too -> https://imagekit.io/use-cases/file-upload/

### Coherent and semantic html

### Accessibility

You can yourself make a test and press [Cmd]+[+], you'll likely zoom on the webpage. This feature is actually used for folks with visual impairments. Think about browser-activated 'dark' feature, text-to-speach devices, etc. There are dozens of thousands of possible combinations of browsers/versions + screen devices + interacting methods (hover/touch). It will be impossible to predict/force all outcomes to look *as* you wish 100%.

It is better to have less differentiation, somewhat a ‘universal’, ‘one-size-fits-all’ approach…

### Mobile-first

### Performance issues

Some CSS properties can consume a lot of ressources. Most of you won't reach the point where your browser will start behaving *slower* but it's possible.

**Tricks**

- filter (blur) and mix-blend-mode, especially if stacked on each others, using high value (for blur), or applied on heavy elements like video.
- use the `will-change` property on the parent of the ressource-heavy element, and specify the energy-hungry property within the `will-change` property.
- Prefer the css `transform` property over `top | left | right | bottom` if you intend to animate (via a transition) the property.
  
## A list of link ressources to perform website tests

Features issues & support:

- Can I use…, support tables for HTML5, CSS3, etc: caniuse.com
- Stack overflow (Q&A for developers, problem-sharing and fixing): stackoverflow.com/questions

Markup testing:

- W3C validator markup testing: validator.w3.org (free)

Cross-device testing:

- Browserstack (test on multiple screens or user agents): browserstack.com (€)

Performance testing / audit:

- Google Lighthouse: developers.google.com/web/tools/lighthouse (Shift + ⌘ + C in Google Chrome)
- Website Speed Test: tools.pingdom.com
- Website Carbon Calculator: websitecarbon.com

Accessibility testing / audit:

- WebAIM: webaim.org/techniques/keyboard (free)
- WAVE (website accessibility evaluation tool): wave.webaim.org (free)
- Web accessibility .com: webaccessibility.com (free, €)
- WebAIM (contrast checker): webaim.org/resources/contrastchecker

Social medias scrapers / debuggers:

- Facebook sharing debugger tool: developers.facebook.com/tools/debug (free)
- Twitter cards validator tool: cards-dev.twitter.com/validator (free)
- LinkedIn post inspector: linkedin.com/post-inspector (free)

Checklists:

- The Front-end check-list github.com/thedaviddias/Front-End-Checklist
- A11y checklist: a11yproject.com/checklist
