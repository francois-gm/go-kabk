# A 'boilerplate'

> Boilerplate text, or simply boilerplate, is any written text (copy) that can be reused in new contexts or applications without significant changes to the original. The term is used in reference to statements, contracts and computer code, and is used in the media to refer to hackneyed or unoriginal writing. (Source: [Wikipedia](https://en.wikipedia.org/wiki/Boilerplate_text))

In order to support good working practices, I suggest people to start with a 'boilerplate'. Within that folder you'll find two boilerplates, one that is only html and another one with an additional CSS boilerplate.

## Why a boilerplate?

Because some elements might not deserve to be rethought of, conceptually (ie standardized things that never/barely change in time).
Because the more you'll work on your project, the more working with a simple and ordered file system appears beneficial.

## About the folder's structure

Since you'd likely benefit from avoiding having endless unordered files of various levels on importance all over, I propose the following:
`/assets/..`
This folder contains elements required for your website to run. These elements are likely to be required on **all** your pages. Inside this folder, you can find a /css subfolder, a /fonts subfolder, a /images subfolder and a /js subfolder.
`/content/..`
Put your images, videos, files, etc there...

Your pages (index.htm but also other pages) can stay on the top level of your folder.

## HTML boilerplate

For the **HTML** boilerplate, here are the following components:

**Head**

- Doctype 'HTML' (the top part, says that it's an HTML5 document)
- The meta viewport tag ( `<meta name="viewport" content="width=device-width,initial-scale=1.0">` ), you need this for the website to work out 'responsively'.
- Meta tags (title, keywords...)
- Favicon links (.png works, 512x512px), before delivery your final webpage you can use https://www.favicon-generator.org to generate your favicons + code
- Open Graph meta tags (for link sharing, maybe not very important unless you want to share your work on a fb/twitter).
- CSS stylesheet links (no CSS in your html document please! neither within `<style>` tags nor as `inline` css properties!)
- Javascript scripts links (no Javascript within `<script>` tags inside your html document, please!)

**Body**

Here, it's not essential to follow this stucture. Nonetheless, using HTML tags in a semantic order is encouraged.

## CSS boilerplate

The CSS boilerplate (`master.css`)includes several elements.

It starts with **@font-face properties**. These properties allow you to import your own font files locally.
You can use [transfonter](https://transfonter.org) to generate web fonts from local files.
You can also find fonts to use on a open-source license there:

- https://usemodify.com
- https://www.velvetyne.fr
- https://fonts.google.com

(if you use fonts that are hosted online you usually have to simply add the link provided to you inside your html `<head>`)

After the @font-face are **CSS global variables**. Here you can add any values that will be re-used extensively within your website. You color palette is probably a good candidate. Margin values can also be. [more on CSS variables](https://www.w3schools.com/css/css3_variables.asp)

Then you'll find (in order):

- **General styles** for most common semantic html tags, like `h1,h2,h3,h4,h5,h6,p,ol,ul,hr`... This will apply to any tags (unspeficity) within your pages.
- **Page styles**, here you can start actually styling your website (!)
- **Usability/Utility classes**: small classes you'll re-use to 'override' previous classes. Here I have included three classes (`.desktop, .mobile, .sr-only`)
- **Media queries**: the breaking points here correspond more or less to *bootstrap*'s standard, although not entirely. Also, by changing the `font-size` value on the `<html>|<body>` elements at different screen sizes (via media queries), you can change the value of a `rem` (*Relative Em*, as a `rem` is equal to the value of `font-size` on the html/body element). It's an easy way to style for various screens, if you already use `rem`'s in your main css styles you won't have to write these lines again within the media queries unless you deem the ratio used previously not appropriate. Here I've already included `font-size` values for different breaking points, but you can change them of course.

## JS boilerplate

I've included JQuery but I've been told some people might also use Javascript ES6. Here, feel free to choose your prefered way of writing but as said again please refrain from including <script> stuff in your html. If JQuery, you need to include your code afte the `$(document).ready(function() {` line. This means that JQuery will load your code after your html document will have been parsed within your browser. The effect is akind of putting your script after the `body` tag.
