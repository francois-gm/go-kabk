# Optimizing 🚀

1. [Proper files ressource size](#1-proper-files-ressource-size)
2. [How properties affect page rendering](#2-how-properties-affect-page-rendering-)
3. [Prefixing properties and property browser support](#3-prefixing-properties-and-property-browser-support)


### In short

- **Use .jpg for images**, avoid .png over 500kb (and use only for transparency or if file is smaller than .jpg), avoid .gif over 500kb (and use only for moving or if smaller than .jpg).
- Consider using .svg files (yes!) instead of .png files
- **Compress your .jpg with Photoshop** using the **'Save for Web (Legacy)'** option (under File->Export), [Shift]+[Alt]+[Cmd]+[S].
- If 'Save for Web (Legacy)' is not available, use **'Export As'** (under File->Export).
- Your **images should not be too big in relationship with the space they occupy**.
- If you use the html `<video>` tag, export your video to .mp4 -> https://cloudconvert.com/mp4-converter and **adjust the quality so you are at under 8mb per minute.**
- Same applies with the `<audio>` tag, use .mp3 -> https://online-audio-converter.com and **adjust so you're under 1mb / minute.**
- If your media file is verrrrrrrrrrrrry heavy, consider using Vimeo, YouTube or Soundcloud and embed it on your website using the provided embed code. Some of these services provide an API to control play/pause, volume, etc, through Javascript.
- If your page is really image-heavy, consider implementing your images with a lazyload: https://afarkas.github.io/lazysizes/index.html, or the browser's default lazy loading option (https://web.dev/browser-level-image-lazy-loading/)
- Use a CDN (Content Delivery Network) to deliver your media files: https://cloudinary.com/ (cloudinary has a free tier, [documentation](https://cloudinary.com/documentation/image_optimization)). Imagekit.io too -> https://imagekit.io/use-cases/file-upload/ 

## 1. Proper files ressource size

If one assumes that among a website's goals, **communication** takes precedence over **archiving**, then optimal page load and appropriate ressoure size are indeed important. Most designers/developers, still, would also find important to avoid too much quality loss. So, it's mostly about finding a *sweet spot* between what's good for the viewer's device and internet connection and what's good for their eyes as well.

### Images (files)

- **Compress your .jpg with Photoshop** using the **'Save for Web (Legacy)'** option (under `File->Export`), `[Shift]+[Alt]+[Cmd]+[S]`, with the appropriate image width resizing and the quality setting between **50** and **60** (target under 250kb, the less the better).
- If 'Save for Web (Legacy)' is not available, use **'Export As'** (under `File->Export`).
- Or, optionally, you can use this mac software called [ImageOptim](https://imageoptim.com/).


**Format**: for raster (pixel-based) images, **always always always .jpg!** .jpg! .jpg! No .tif, and no other fancy image formats.

You **might** get away with the following:

- A .gif **IF** it's animated and small (like 200-300 pixels wide) and you make sure your .gif is under 250kb…
- A .png **IF** it uses transparency and it's under 250kb…
- A .gif or a .png **IF** they are compressed with **only 2 or 4 colors** and because of that they weight less than their .jpg equivalent at same size…
- **IF** it's not a raster image you can use .svg, which is vector-based (not pixel-based). Advantages of .svg files are that they can scale at any size and their weight are very small. Good for logos and buttons…

**Dimensions**: a width of **2400px** if the image will be displayed on the full width of the screen (taking 100% of your browser's width), **1200px** if the image takes **half of your screen**. A 'retina' screen displays at a density of between 2x and 3x, so by aiming at a bit under 2x the size of a physical screen you should be good.
**Target file size**: **75kb - 200kb** per image, depending on the image dimensions, whether it should take a full screen size or not.
In photoshop, a compression rate (quality level) at 50-60% is sufficient without compromising the appearance.

### Images (delivery)

#### Lazy loading

Code-wise, you can also use **lazy loading** if loading lots of images. What is lazy loading? Lazy loading is a method to **only load images when they are close to the point of appearing on the screen**, which can **saves time and ressources**.

Since recently, it's possible to use lazy loading *without any plugins*, straight from the browser by adding a `loading='lazy'` attribute to your `<img>` tag. The method is supported by [around 70% of web browsers](https://caniuse.com/loading-lazy-attr) (on caniuse.com). See [how it works](https://www.w3schools.com/tags/att_img_loading.asp) (on W3schools), or [read more here](https://web.dev/browser-level-image-lazy-loading/) (on web.dev).

If you'd like to implement lazy loading and are fine to put more time to it to support 99% instead of 70% of browsers, you can also use ressources such as [the lazysizes javascript plugin](https://afarkas.github.io/lazysizes/index.html).

#### Using the srcset attribute

You can also control which image you provide the viewer with depending on their device screen size using the srcset properties. This can be useful if, let's say you have a lot of full sized images on your design and you don't want to provide mobile visitors with 2400 pixel wide images (!), thus saving them some precious data.

Read more: [Extensive reading](https://css-tricks.com/a-guide-to-the-responsive-images-syntax-in-html/) (on css-tricks), [another extensive reading/guide](https://medium.com/@woutervanderzee/responsive-images-with-srcset-and-sizes-fc434845e948) (on medium.com), [*Kind of* straightforward guide](https://webdesign.tutsplus.com/tutorials/quick-tip-how-to-use-html5-picture-for-responsive-images--cms-21015).

Example:

```
<img 
  alt="A wooden old round table with a green apple on it."
  src="table-s.jpg"
  srcset="
    table-s.jpg  300w,
    table-m.jpg  600w,
    table-l.jpg  1200w,
    table-xl.jpg 2000w
  "
  sizes="100vw"
>
```

On that example, a default image is defined (with the `src` attribute) and four images are then provided with `srcset`, at sizes of `300w`, `600w`, `1200w` and `2000w` (here, the **w** for width is the pixel width of your image). Then, the `sizes` attribute says that the image will be displayed at 100vw, which means full screen (100 viewport width units = 100% of the screen width). The sizes attribute also takes media queries, so as an example you can tell that if the device screen is smaller the image will be full sized but on a bigger screen they will only be 50% wide.

Note that there are no rules about the amount of images you should provide (this depends on your design proposal). **The lazy loading and srcset properties are combinable.**

### Other media files

- Videos: if using your own files within the `<video>` tag, the preferable file format is **.mp4**, use [this video converter for that purpose](https://cloudconvert.com/mp4-converter), and try to keep it at **8mb / minute**. After Effects and Premiere settings should give fine results with **h.264** and a **bitrate compression rate of +/- 2.0**.
- Sound: if using your own files within the `<audio>` tag, the preferable file format is **.mp3**, use [this audio converter for that purpose](https://online-audio-converter.com), and try to keep it at **1mb / minute**.
- Embedded file: If your media files are heavy, consider using Vimeo, YouTube or Soundcloud and embed them on your website inside `<iframe>` tags using the provided embed code. Some of these services provide an API to control play/pause, volume, etc, through Javascript.

### Fonts

- **.woff2** is your friend. Use tools like [transfonter.org](https://transfonter.org) (or [fontsquirrel.com](https://www.fontsquirrel.com/tools/webfont-generator)) to generate your font files! It's okay to include other file formats as fallback (if the browser does not support `woff2` which should be pretty rare in 2022). When dealing with 'fallbacks' you declare first your *best* option (so `woff2` is the best, so it goes first).

### General

- If you have a lot of files, and it's very heavy, especially media files, you can also use a CDN (Content Delivery Network) to deliver your media files: https://cloudinary.com/ (cloudinary has a free tier, [documentation](https://cloudinary.com/documentation/image_optimization)). Imagekit.io too -> https://imagekit.io/use-cases/file-upload/ 

## 2. How properties affect page rendering 🐌

Some CSS properties can consume a lot of ressources. Most of you won't reach the point where your browser will start behaving *slower* but it's possible.

**Tricks**

- Be careful of not overusing the css `filter` (especially `filter: blur(value)`) and mix-blend-mode properties, especially if stacked on each others, using higher value (for blur), or applied on ressource heavy elements like video.
- Animations can consume a lot too. Some properties are more 'expensive' than others to be animated. Prefer the css `transform` property over `top | left | right | bottom` if you intend to animate (via a transition) the property. [Read more](https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/) (*old*-ish ressource but still valid)
- Use the `will-change` property on the parent of the ressource-heavy element, and specify the energy-hungry property within the `will-change` property. [more on MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/will-change). This will force the browser to allocate some processing power to render the ressource, thus reducing lagging / slowness.

## 3. Prefixing properties and property browser support

Sometimes some css properties work on 70-80% of browsers, and for others you need to 'prefix' it. If you're having troubles having consistent appearance only in some browsers (like, it works on Chrome but not Firefox), then make sure to double-check on https://www.caniuse.com . Here's an [example with variable fonts](https://caniuse.com/?search=variable%20fonts), where we can see that although it seems to work on 95% of browsers there are still some sub-properties that aren't supported by every browsers.

Some properties might need do be also declared with prefixing to support older browser. Examples are:

- `position: sticky;` could also be declared like that: `position: -webkit-sticky;` (for Safari, below 2017?)
- `transform: scale(2);` could also be declared like that: `-webkit-transform: scale(2);` (for Safari, below 2016?)

When you declare prefixed properties, you declare them in **addition** to the unprefixed properties.

*As time passes by, whether a property needs to be prefixed as well or not depends on who's your audience.*
