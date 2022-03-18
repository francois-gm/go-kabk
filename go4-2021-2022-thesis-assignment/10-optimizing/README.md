# Optimizing

1 - Proper ressource size
2 - How properties affect page rendering
3 - A bug is a rule

## 1. Proper ressource size

If one assumes that among a website's goals, **communication** takes precedence over **archiving**, then optimal page load and approriate ressoure size are indeed important.

Most designers/developers, still, would also find important to avoid too much quality loss. So, it's mostly about finding a sweet spot between what's good for the viewer's device and internet connection and what's good for their eyes as well.

### Images

Image are important, and might get used a lot. The more there are, the more it becomes important and relevant to ensure they are delivered with at appropriate dimensions and file size.

- **Compress your .jpg with Photoshop** using the **'Save for Web (Legacy)'** option (under File->Export), [Shift]+[Alt]+[Cmd]+[S], with the appropriate image width resizing and the quality setting at **60** or below.
- If 'Save for Web (Legacy)' is not available, use **'Export As'** (under File->Export).

**Format**: for raster (pixel-based) images, **always always always .jpg!** .jpg! .jpg! No .tif, and no other fancy image formats.
\* You **might** get away with the following
- A .gif **if** it's animated and small (like 200-300 pixels wide) and you make sure your .gif is under 250kb
- A .png **if** it uses transparency and it's under 250kb
- A .gif or a .png **if** they are compressed to only 2 or 4 colors and because of that they weight less than their .jpg equivalent at same size.
- **if** it's not a raster image you can use .svg, which is vector-based (so no rasters-pixels). Advantages are that it can scale at any size and it weight small. Good for logos and buttons.

**Dimensions**: a width of **2400px** for a **full size** design (an image that takes 100% of your browser), **1200px** if the image takes **half of your screen**. A 'retina' screen displays at a density of between 2x and 3x, so by aiming at a bit under 2x the size of a physical screen you should be good.
**Target file size**: **75kb - 200kb** per image, depending on the image dimensions, whether it should take a full screen size or not.
In photoshop, a compression rate (quality level) at 50-60% is sufficient without compromising the appearance.

### Other media files

- Videos: if using your own files within the `<video>` tag, the preferable file format is **.mp4**, use this video converter for that purpose: https://cloudconvert.com/mp4-converter, and try to keep it at **8mb / minute**. After Effects and Premiere settings should give fine results with h.264 and a bitrate compression rate of +/- 2.0.

- Sound: if using your own files within the `<audio>` tag, the preferable file format is .mp3, use this audio converter for that purpose: https://online-audio-converter.com, and try to keep it at **1mb / minute**.

### Fonts

- **.woff2** is your friend. Use https://transfonter.org (or https://www.fontsquirrel.com/tools/webfont-generator) to generate your font files! It's okay to include other file formats as fallback (if the browser does not support woff2 which should be pretty rare in 2022). When dealing with 'fallbacks' you declare first your *best* option (so woff2 is the best, so it goes first).

---



## *Block* or *inline*?

*Block* and *inline* are two types of layout behaviors for HTML tags. A block element always starts on a new line, takes up the full available width (stretches out to the left and right as far as it can), and has a top and a bottom margin. Divs and HTML5 semantic layout tags are block elements. An inline element does not start on a new line and only takes up as much width as necessary.

Default behavior:

- **block** – `div`, `ul`, `li`, `nav`, `main`, `p`, etc...
- **inline** – `span`, `a`, `strong`, etc... 

Read more: http://web.simmons.edu/~grovesd/comm244/notes/week4/block-inline

The behavior can be explicitely stated with CSS:

- `display: block;` – always starts on a new line and takes up the full width available.
- `display: inline;` – does not start on a new line and only takes up as much width as necessary.
- `display: inline-block;` – like inline but does allow width and height properties.
- `display: none;` – the element is not visible and not in the flow of the document.

Two other properties are also relevant to control how elements behave between themselves (if used with position: static and position: relative), `float` and `clear`. The CSS `float` property specifies how an element should float in regard to surrounding elements. Valid values are `float: left;`, `float: right;`, and `float: none;`. [See examples of floating elements](https://www.w3schools.com/css/css_float_examples.asp), on the w3cschool.com.

The CSS `clear` property specifies if elements can float beside the cleared element and on which side. Valid values are `clear: left;`, `clear: right;`, `clear: both;` and `clear: none;`. [See examples of clear elements](https://www.w3schools.com/css/https://www.w3schools.com/css/css_float_clear.asp), on the w3cschool.com.

## CSS Position

The position property has the following possible values:

- `position: static;` – positioned according to the normal flow of the document and not affected by top, right, bottom, left and z-index properties (default value).
- `position: relative;` – positioned according to the normal flow of the document, and then offset relative to itself based on the top, right, bottom and left values (if defined). Also affected by the z-index property (if defined).
- `position: absolute;` – removed from the normal document flow (no space is created for the element in the page layout). Positioned relative to its closest parent, and position defined by the top, right, bottom and left values.
- `position: fixed;` – same as absolute, but positioned relative to the viewport window, and always stays at the same location.
- `position: sticky;` – positioned according to the normal flow of the document (like relative), but becomes fixed once the scrolling position reaches one of the defined sides of the element (the top, right, bottom or left value needs to be defined to make it work). The element ‘sticks’ momentarily. (CSS 3.0 value).

## Layout with CSS flexbox and grid

### Flexbox

> "Legacy web CSS layouting has worked so far with elements defined as either block or inline that are made to float and clear in a relation between the previous (left) and next (right) element. This has previously worked fine when used in combination with percentages for responsive layouts, but this method has shown its when taking contemporary standards of responsiveness into account."

Flexbox offers the possibility to specify via the container the presentation behavior of its children, as well as to push for element-specific overriding of the general container rules. A flexbox container is defined by the property `display: flex;`. Further `flex` properties are defined to control the presentation and ordering.

![Flexbox](flexbox-basic-terminology.svg)

Parent (container) properties:

- `flex-direction`: *row, row-reverse, column, column-reverse*
- `flex-wrap`: *nowrap, wrap, wrap-reverse* (either the content line clears or squeezes itself if content overloads)
- `justify-content`: *flex-start, flex-end, center, space-between, space-around, space-evenly*
- `align-items`: *flex-start, flex-end, center, stretch, baseline*
- `align-content`: *flex-start, flex-end, center, stretch, space-between, space-around*

Properties for the children (optional but allow more control):

- `order`: number, allows a custom ordering based on the priority number of each child.
- `flex-grow`, `flex-shrink`, `flex-basis`: growing, shrinking, and default sizing behaviour.
- `align-self`: overrides the parent alignment (values are the same that align-content).

Learn everything about flexbox with examples through [CSS trick's A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/).

### Grid

The CSS grid module is a recent addition to CSS (2017+) that offers deeper possibilities for layout than flexbox. The CSS grid is two dimensional, and works similarly to flexbox. A grid container is defined by the property `display: grid;`. Further `grid` properties are defined to control the rows and columns.

![Grid](flexbox-vs-grid.png)

Parent (container) properties:

- `grid-template-columns`: absolute unit (`px`), relative (`%`, `rem`), or `fr` (fraction of total size)
- `grid-template-rows`: absolute unit (`px`), relative (`%`, `rem`), or `fr` (fraction of total size)
- `grid-template-area`: defines area within the grid
- `column-gap`,`row-gap`: flex-start, flex-end, center, stretch, baseline

Like flexbox, the container also has justification and alignment properties.

Properties for the children (optional but allow more control):

- `grid-row-start`, `grid-row-end`, `grid-column-start`, `grid-column-end`: determines a grid item’s location within the grid by referring to specific grid lines.
- `grid-area`: used to reference to areas set on the parent with *grid-template-area*.
- `justify-self`, `align-self`, `place-self`: justification and/or alignment within a cell (start, end, center, stretch).

Learn everything about grid with examples through the [Complete Guide to Grid target](https://css-tricks.com/snippets/css/complete-guide-grid/), on *css-tricks.com*

Ressource: use the [CSS Grid Generator](https://grid.layoutit.com), on *grid.layoutit.com*

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

## Object-fit

> The CSS `object-fit` property is used to specify how an `<img>` or `<video>` should be resized to fit its container. This property tells the content to fill the container in a variety of ways; such as "preserve that aspect ratio" or "stretch up and take up as much space as possible". From [Object-fit](https://www.w3schools.com/css/css3_object-fit.asp) on *w3schools.com*

