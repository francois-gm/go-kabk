# CSS layout units exercise

## a) Download `exercise-unit-a.zip`

Open the index.html and style.css, and let's do some changes...

- Changing **`width`** of a selector with **`px`** value.
- Changing **`width`** of a selector with **`%`** value.
- Changing **`width`** of a selector with **`vw`** value.
- Changing **`width`** of a selector with **`vmin`** value.
- Changing **`height`** of a selector with **`px`** value.
- Changing **`height`** of a selector with **`%`** value.
- Changing **`height`** of a selector with **`vh`** value.
- Changing **`height`** of a selector with **`vmin`** value.

## b) Download `exercise-unit-b.zip`

Open the index.html and style.css, and let's do some changes...

- Block A takes the **full width *minus* block B**, Block B has **fixed width**.
- Block A takes a **percentage plus a fixed value**, Block B takes a **percentage minus a fixed value**.
- Try **other combinations** and look at the behaviour (**while resizing your window**).

Advanced option with CSS variable:

```
// first a CSS variable is defined for the website's 'margin' size. This combines responsive with fixed units.
:root {
  --margin-unit: calc(2.5vw + 1rem);
}

// Then the CSS variable is used as the margin of our block. The padding is defined as half of a 'margin' unit.
div {
  margin: var(--margin-unit);
  padding: calc(var(--margin-unit) * 0.5);
}
```
