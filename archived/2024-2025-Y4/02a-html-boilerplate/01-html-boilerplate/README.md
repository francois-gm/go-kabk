# Starting right (with a HTML boilerplate/starterkit)

To support good working practices, let's make sure we have the same foundation. 

Within this page, you'll find two options, one that has only html elements, and another one with an additional an CSS starter stylesheet.

## Why a boilerplate?

- Because some *standards* don't need to be thought, and don't change.
- And because the more you'll work on your project, the more having a some order becomes beneficial.

## About the folder's structure

Your website folder will include several files and sub-folders. With a few, it's fine, but the bigger it gets, the more it becomes important to have a logical way to order all that.

For your **website ressource**, let's order them in this sub-folder:

- `/assets/..`

This folder contains elements required for your website to run. These elements are likely to be required on **all** your pages. Inside this folder, you can find a `/assets/css` subfolder, a `/assets/fonts` subfolder, a `/assets/images` subfolder and a `assets/js` subfolder.

For your **website contents**, let's order them in this sub-folder:


- `/content/..`

Put your images, videos, files, etc there...

Your pages (index.html but also other pages) can stay on the top level of your folder.

## The HTML boilerplate

For the **HTML** boilerplate, here are the following components:

**Head**

- Doctype 'HTML' (the top part, says that it's an HTML5 document)
- The meta viewport tag ( `<meta name="viewport" content="width=device-width,initial-scale=1.0">` ), you need this for the website to work out 'responsively'.
- Meta tags (title, keywords...)
- Favicon links (.png works, 512x512px), before delivery your final webpage you can use https://www.favicon-generator.org to generate your favicons + code
- CSS stylesheet links (no CSS in your html document please! neither within `<style>` tags nor as `inline` css properties!)
- Javascript scripts links (no Javascript within `<script>` tags inside your html document, please!)

**Body**

Here, it's not essential to follow this stucture. Nonetheless, using HTML tags in a semantic order is encouraged.

## CSS boilerplate

The CSS boilerplate (`style.css`)includes several elements.

It starts with **@font-face properties**. These properties allow you to import your own font files locally.
You can use [transfonter](https://transfonter.org) to generate web fonts from local files.
You can also find fonts to use on a open-source license there:

- https://www.velvetyne.fr
- https://usemodify.com
- https://www.design-research.be/by-womxn/
- https://v-fonts.com/licenses/open-source
- https://fonts.google.com

(if you use fonts that are hosted online you usually have to simply add the link provided to you inside your html `<head>`)

## CSS variables

In order to make our life easier, we'll be adding (after the @font-face property) our **CSS global variables**. CSS variables (here, declared globally withint the 'root' selector) can be re-used extensively within your website. Using CSS variables for you color palette is probably a good candidate. Margin values can also be. [More on CSS variables](https://www.w3schools.com/css/css3_variables.asp).

Further links on CSS variables:

- Ressource: https://css-tricks.com/a-complete-guide-to-custom-properties/
- Example: https://codepen.io/chriscoyier/pen/ORdLvq?editors=0110

## CSS file order

Then you'll find (in order):

- **General styles** for most common semantic html tags, like `h1,h2,h3,h4,h5,h6,p,ol,ul,hr`... This will apply to any tags (unspeficity) within your pages.
- **Page styles**, here you can start actually styling your website (!)
- **Usability/Utility classes**: small classes you'll re-use to 'override' previous classes. Here I have included three classes (`.desktop, .mobile, .sr-only`)
- **Media queries**: the breaking point values are pretty standard here. Also, by changing the `font-size` value on the `<html>|<body>` elements at different screen sizes (via media queries), you can change the value of a `rem` (*Relative Em*, as a `rem` is equal to the value of `font-size` on the html/body element). It's an easy way to style for various screens.

Further links on CSS media queries:

- Ressource: https://css-tricks.com/a-complete-guide-to-css-media-queries/
- Examples: https://www.w3schools.com/css/css_rwd_mediaqueries.asp

## JS boilerplate

Plain, modern Javascript for interactivity is wrapped into a 'document loaded' function. This allows you to have your script file in your HTML 'head'.
