# What about footnotes? 📖

There are no specific html tags that define footnote elements. Instead, these are built based on what's available, and although footnotes tend to follow standards, they might also deviate from 'common' practices.

Consider this snippet:

```

<article>
  <p>
    This is a footnote.<sup class="footnote"><a id="fnref-1" href="#fn-1">1</a></sup>
    Here's another one.<sup class="footnote"><a id="fnref-2" href="#fn-2">2</a></sup>
    And, a third footnote in here.<sup class="footnote"><a id="fnref-3" href="#fn-3">3</a></sup>
  </p>
</article>

<footer>
  <ol class="footnotes-list">
    <li id="fn-1" value="1">
      Right here! <span class="footnotereverse"><a href="#fnref-1">↩</a></span>
    </li>
    <li id="fn-2" value="2">
      Yes, another one. </a><span class="footnotereverse"><a href="#fnref-2">↩</a></span>
    </li>
    <li id="fn-3" value="3">
      All good! <span class="footnotereverse"><a href="#fnref-3">↩</a></span>
    </li>
  </ol>
</footer>


```

In the previous examples, footnotes are produced by using links with anchor (`#anchor`) target. By using ID attributes, it's possible to link to a footnote and link the footnote back to the reference. This example places footnotes at the end of the page (footer), inside an ordered list (`ol`) which prepended numbering to the footnote by function, but there are of course other possibilities. Foonotes could be placed `aside`, or within the text (as tooltips / popups).

More examples:

- Default and accessible html footnotes with hyperlinks (similar to the previous example): https://codepen.io/SitePoint/pen/QbMgvY
- Footnotes as 'tooltips', with vanilla javascript: https://goblindegook.github.io/littlefoot/
- ~~JQuery Sidenotes: https://acdlite.github.io/jquery.sidenotes/ (old, deprecated)~~
- ~~Bruno Correia's Sidenotes.js https://github.com/bcorreia/sidenotes.js~~
- Tufte CSS: https://edwardtufte.github.io/tufte-css/
- Example variation on Tufte CSS (custom, using Javascript): http://contemporary-home-computing.org/affordance/
- ~~Molly White's Annotate.js https://github.com/molly/annotate~~
- For reading, sidenotes in web design: https://www.gwern.net/Sidenotes
- And their own (up-to-date) implementation of `sidenotes.js` https://gwern.net/sidenote#sidenotes-js (generates sidenotes from Pandoc **endnotes**)
