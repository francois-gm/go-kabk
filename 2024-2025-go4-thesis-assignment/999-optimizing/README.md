# Optimizing 🚀

1. [Proper files ressource size](#1-file-risizing-and-delivery-in-short)
2. [How properties affect page rendering](#2-how-properties-affect-page-rendering-)

## 1. *File resizing and delivery, in short*

- **Use .jpg for images**, avoid .png (only if transparency) and .gif (only if animated).
- Try to target **250kb** per image.
- Consider using .svg files (yes!) instead of .png files.
- **Compress your .jpg with Photoshop** using the **'Save for Web (Legacy)'** option (under File->Export), [Shift]+[Alt]+[Cmd]+[S]. Choose **50–60** for quality.
- If 'Save for Web (Legacy)' is not available, use **'Export As'** (under File->Export).
- Or **compress your images online using Squoosh**, https://squoosh.app.
- Target an image (physical) size in pixels of 1.5 times the maximum display size you can reasonably expect.
- If you use the html `<video>` tag, export your video to .mp4 -> https://cloudconvert.com/mp4-converter and **adjust the quality so you are at under 8mb per minute.**
- Same applies with the `<audio>` tag, use .mp3 -> https://online-audio-converter.com and **adjust so you're under 1mb / minute.**
- If your media file is too heavy, consider using Vimeo, YouTube or Soundcloud and embed it on your website using the provided embed code. Some of these services provide an API to control play/pause, volume, etc, through Javascript.
- If your page is image-heavy, consider implementing your images with a lazyload: https://afarkas.github.io/lazysizes/index.html, or the browser's default lazy loading option (https://web.dev/browser-level-image-lazy-loading/)

### Fonts

- **.woff2** is your friend. Use tools like [transfonter.org](https://transfonter.org) (or [fontsquirrel.com](https://www.fontsquirrel.com/tools/webfont-generator)) to generate your font files! When dealing with 'fallbacks' you declare first your *best* option (so `woff2` is the best, so it goes first).

### General

- If you have a lot of files, and it's very heavy, especially media files, you can also use a CDN (Content Delivery Network) to deliver your media files: https://cloudinary.com/ (cloudinary has a free tier, [documentation](https://cloudinary.com/documentation/image_optimization)). Imagekit.io too -> https://imagekit.io/use-cases/file-upload/ 

## 2. How properties affect page rendering 🐌

Some CSS properties can consume a lot of ressources. Most of you won't reach the point where your browser will start behaving *slower* but it's possible.

**Tricks**

- Be careful of not overusing the css `filter` (especially `filter: blur(value)`) and mix-blend-mode properties, especially if stacked on each others, using higher value (for blur), or applied on ressource heavy elements like video.
- Animations can consume a lot too. Some properties are more 'expensive' than others to be animated. Prefer the css `transform` property over `top | left | right | bottom` if you intend to animate (via a transition) the property. [Read more](https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/) (*old*-ish ressource but still valid)
- Use the `will-change` property on the parent of the ressource-heavy element, and specify the energy-hungry property within the `will-change` property. [more on MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/will-change). This will force the browser to allocate some processing power to render the ressource, thus reducing lagging / slowness.
