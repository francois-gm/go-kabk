# CSS layout

## The *display* property: *Block* and *inline*?

*Block* and *inline* are two value types of basic layout behaviors for HTML tags. 

A **block** element always starts on a new line, takes up the full available width of the parent (stretches out to the left and right as far as it can), and has a top and a bottom margin. A **`<div>`** is a block element, as well as most non-typography html elements and elements that are containers for typography (think of **`<p>`**).

An **inline** element does not start on a new line and only takes up as much width as necessary. This is the behaviour of typography-based html elements like the **`<sup>`** (footnote marker), the **`<span>`** or **`<a>`** (hyperlinks).

Elements have their display behaviour defined by default, but they can be defined with CSS through following property:

```
.myclass{
  display: block;
}
```

... or

```
.myclass{
  display inline;
}
```

In addition:

- `display: inline-block;` – like inline but does allow width and height properties.
- `display: none;` – the element is not visible and not in the flow of the document.

See a demo of 'inline' elements: http://web.simmons.edu/~grovesd/comm244/notes/week4/inline-demo-outlines. <br>
See a demo of 'block' and 'inline' elements: http://web.simmons.edu/~grovesd/comm244/notes/week4/block-inline-demo.

## The *float* and *clear* properties

*Float* and *clear* are CSS properties that specify how an element will behave in relationship to the next one. In an way, what they do are akin to **line breaks** for text, but with with HTML *block* elements.

```
.myclass{
  display: block;
  float: left; // the element floats to the left
  clear: right; // the element after this element will float right of this element, if there is enough space
}
```

Floating elements can have 'float' `left` or `right` values.

Floating element scan have 'clear' `left`, `right` or `both` (goes on the new line, below) values.

See examples of [floating elements](https://www.w3schools.com/css/css_float_examples.asp) and [clear elements](https://www.w3schools.com/css/css_float_clear.asp), on the w3cschool.com.

## The *position* property

There are several behaviours tyoes for positioning your elements with CSS. 

* `position: relative;` - relatively to the position of the previous HTML element, within the parent element. When using 'relative' you might also combine it with 'float' and 'clear' properties.
* `position: absolute;` - based on values defined by you (top, bottom, right, left), within the parent element.
* `position: fixed;` - based on values defined by you (top, bottom, right, left), and stays fixed: is not affected by scrolling.
* `position: sticky;` - a mix between relative and fixed (elements seem like 'sticking' when scrolling).

```
// the element is fixed at the bottom right part of the page

.myclass{
  position:fixed;
  display: block;
  right: 10px;
  bottom: 10px;
}
```

## *Margin* and *padding* properties

- Margin: space **outside** of the block.
- Padding: space **inside** the block.

### The box model

The *box model* is a representation of the html elements' expected behaviour regarding margin, padding, borders values and the inner content of an element. This visual model is also used in your browser's 'developers tool', so if you’re working on or analyzing a website you’ll see it.

The css property `box-sizing` can be used to impact how the `padding` property is calculated in relationship to the width or height of the element. ([Read more on w3schools.com](https://www.w3schools.com/css/css3_box-sizing.asp))

![The box model](box-model.png)

## CSS length units

Some units useful for layouting:

- `vw` - Relative to 1% of the width of the viewport*
- `vh` - Relative to 1% of the height of the viewport*
- `vmin` - Relative to 1% of viewport's* smaller dimension
- `vmax` - Relative to 1% of viewport's* larger dimension
- `%` - Relative to the parent element

\* Viewport = the browser window size. If the viewport is 1200px wide, 1vw = 12px.

## CSS calc(), and min-max properties

Sometimes you would like to combine two different types of units in one value (!) You can do this with the `calc()` function.

```
width: calc(100% - 20px);
width: calc(100vmax - 2rem);
width: calc( (100% / 6) - (1rem * 2) );
padding: calc(1rem * 0.75 );
font-size: calc(0.75rem + 2.5vw);
…
```

## Layout with CSS flexbox and grid

### Flexbox (recommended)

Flexbox is offers the possibility to specify via the *parent container* the presentation behavior of elements inside it. 

The *parent container* has the property value `display: flex;`.

Optional properties and values for flexbox (after setting **display: flex;**):

Use these on the parent (container):

- `flex-direction`: *row, row-reverse, column, column-reverse* - Chooses the presentation direction of children elements.
- `flex-wrap`: *nowrap, wrap, wrap-reverse* - Either the content line **is cleared** (wrap) or **squeezes itself** (nowrap) within the line if content overloads.
- `justify-content`: *flex-start, flex-end, center, space-between, space-around, space-evenly*
- `align-items`: *flex-start, flex-end, center, stretch, baseline*
- `align-content`: *flex-start, flex-end, center, stretch, space-between, space-around*

Use these on the children (optional):

- `order`: number, allows a custom ordering based on the priority number of each child.
- `flex-grow`, `flex-shrink`, `flex-basis`: growing, shrinking, and default sizing behaviour.
- `align-self`: overrides the parent alignment (values are the same that align-content).

👉 Additional 'cheat-sheet' ressource (recommended): ✨[CSS trick's A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)✨.

### Grid (advanced only)

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
