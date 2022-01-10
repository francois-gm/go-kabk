# Unpacking the webpage

Recap / notions / requirements (unpacking a good website). 
Semantic html + css - user/device/browser agnostic - accessible

Who / when / where / how a website is accessed / consumed…
A website is a tool/platform/container for accessing content, and CSS offers directions regarding appearance (not obligations). User-centered, user agnostic… Separation of concerns (as Thomas suggested)

- Ressources loads fast (under 300ms) [^1] or are splitted to avoid excessive load times
- Interaction elements are properly timed (300ms, no endless transitions)
- Coherent, semantic, and acknowledge expectable design patterns.
- Suggests the website structure/hierarchy in the design (breadcrumbs, menu as sitemap, table of contents). Where am I?
- Avoid interfering with native/expected browser behaviors and user preferences (scrolling functionalities, light/dark modes, cursor suggesting an element can be clicked, etc). 
- Looks fine on any devices, screen sizes, interaction methods: 60% users on mobile devices (1 column, menu shortcuts, touch event), 40% on desktop (1 or multi-column, extended menu, mouse hover), phablets, foldable phones, mega-big ipads, etc…
- Agnostic of language directions (left-to-right, right-to-left)
- Is understandable / accessible without CSS (uses appropriate html tags and page structure). Can be navigated with ‘tabs’ / focus, and screen readers (visual impairments, hearing impairment, etc).
- Takes into account a ‘performance’ budget for client-side features / properties that are resource-intensive (animating a css ‘filter’ blur property can be very demanding).

[^1] https://ux.stackexchange.com/questions/66604/optimal-duration-for-animating-transitions 

Sharing of resources / help regarding points up


Focus points:

- Your website is accessible, legible, and semantically-written (you use correct <html> tags).
- Your website is also optimized for mobile views (it is actually conceived 'mobile-first', you've started your design process with mobile screens in mind).
- Your website loads moderately fast (information is compressed accordingly and you aren't trying to put .tiff images)
