# CSS basic layout exercise

## a) Have a look at the two examples:

- 'inline' elements: http://web.simmons.edu/~grovesd/comm244/notes/week4/inline-demo-outlines. <br>
- 'block' and 'inline' elements: http://web.simmons.edu/~grovesd/comm244/notes/week4/block-inline-demo.

## b) Go at: https://www.kabk.nl/en/

- Do 'command + shift + C' (the shortcut for accessing your browser's *developer tools*)
- Create a new stylesheet rule from your browser inspector (click on the '+' button in Chrome):

```
// '*' means 'every elements'

* {
 outline: 1px solid #F00;
}
```

Look at the page, resize it, and look at how blocks behave. Can you see 'block' and 'inline' elements?

## c) Download `exercise-basic.zip`, open the index.html and style.css, and let's do some changes...

(*document has 12 blocks, relatively positionned*)

- Adding margin to one element
- Adding padding to another element
- Adding a border to that same element
- Adding 'box-sizing: border;' to that same element
- Remove margin on your element you added margin
- Adding 'clear: both' on an element of your choice
- Changing one element to 'position: absolute;' (and play with the **bottom** and **right** properties)
- Changing one element to 'position: fixed;'
