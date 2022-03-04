# CSS layout

## The box model

The CSS box model is essentially a box that wraps around every HTML element. It is a **conceptual representation** (and not an actual property), that helps understand how margin, padding, borders values and the inner content of an element behave between each others. This visual model is used in developers tool, so if you’re working on or analyzing a website you’ll see it. Read more about the box model, on the w3cschool.com.

The css property `box-sizing` can be used to impact how the `padding` property is calculated in relationship to the width or height of the element.

![The box model](box-model.png)

Read more: https://css-tricks.com/the-css-box-model/
Interactive example: http://web.simmons.edu/~grovesd/comm244/notes/week6/box-layout-demo.html

## *Block* or *inline*?

*Block* and *inline* are two types of layout behaviors for HTML tags. A block element always starts on a new line, takes up the full available width (stretches out to the left and right as far as it can), and has a top and a bottom margin. Divs and HTML5 semantic layout tags are block elements. An inline element does not start on a new line and only takes up as much width as necessary.

Default behavior:

- **block**: `div`, `ul`, `li`, `nav`, `main`, `p`, etc...
- **inline**: `span`, `a`, `strong`, etc... 

Read more: http://web.simmons.edu/~grovesd/comm244/notes/week4/block-inline

- `display: inline;` – does not start on a new line and only takes up as much width as necessary.
- `display: block;` – always starts on a new line and takes up the full width available.
- `display: inline-block;` – like inline but does allow width and height properties.
- `display: none;` – the element is not visible and not in the flow of the document.

## Flexbox, grid

- `display: flex;`
- `display: grid;`

## CSS Position

- `position: fixed;`
- `position: absolute;`
- `position: relative;`
- `position: sticky;`



