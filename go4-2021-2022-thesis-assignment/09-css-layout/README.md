# CSS layout

## The box model

The CSS box model is essentially a box that wraps around every HTML element. It is a **conceptual representation** (and not an actual property), that helps understand how margin, padding, borders values and the inner content of an element behave between each others. This visual model is used in developers tool, so if you’re working on or analyzing a website you’ll see it. Read more about the box model, on the w3cschool.com.

The css property `box-sizing` can be used to impact how the `padding` property is calculated in relationship to the width or height of the element.

![The box model](box-model.png)

- Read more: https://css-tricks.com/the-css-box-model/
- Cool interactive demo example: http://web.simmons.edu/~grovesd/comm244/notes/week6/box-layout-demo.html

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

## Layout with CSS flexbox and grid

> "Legacy web CSS layouting has worked so far with elements defined as either block or inline that are made to float and clear in a relation between the previous (left) and next (right) element. This has previously worked fine when used in combination with percentages for responsive layouts, but this method has shown its when taking contemporary standards of responsiveness into account."

- `display: flex;`
- `display: grid;`
