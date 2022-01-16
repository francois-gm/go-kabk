# How-to-how

Common issues...

- [Typos](#typos)
- [Refresh issues, cache](#refresh-issues-website-doesnt-appear-with-new-changes-cache-issues)
- [Finding information online](#finding-information-online)
- For ressources, also see the ressource part of this Github's previous page, **[→ unpacking the webpage=](../2-unpacking-the-webpage#ressources-)**

## Typos

Sometimes it doesn't work because there is a typo, and it can prove frustrating because one assumes the problem to be deeper and ends up being superficial.

### HTML

- Are your html tags opend `<div>` and closed `</div>`?
- Did you forget to close a tag?
- Some tags don't need to be closed, like `<br>`, `<hr>`, `<img>`...
- Are the links to your ressources loading? Sometimes you have to make sure you go back one level if your document and your ressources are in different folders, so `/folder/ressource.js` might not work but `.../folder/ressource.js` will. You can also test your ressource links by user the browser's developer tools.

### CSS

- Are brackets opened and **closed**
- Is the punctuation mark between your property and your value a colon, `:`, and is your punctuation mark after the value a semicolon, `;` (as in `color:blue;`)

## Refresh issues, website doesn't appear with new changes (cache issues)

- Always test your website using your browser's '**private navigation**' mode, to make sure your browser's cache doesn't impact what you see. If your changes don't appear, close and re-open the browser and make sure you're in private mode. You can also append (add) `?ver=1.1` and increment this to your .css and .js stylesheets to force cache reload (to force other visitor's cache if you deploy your website again online). ([more](https://stackoverflow.com/questions/1614429/what-is-style-cssver-1-tag))

## Finding information online

If you're able to summarize your issue, it's quite possible someone has asked about it before online. **Use google and enumerate your issue in a simple sentence**, trying to be as **brief and explicit** as possible. Don't forget to **mention the programming language**. Popular places to read about previous user issues and how they solved them are [Stackoverflow](https://stackoverflow.com) and [CSS Tricks](https://css-tricks.com). Besides, the [w3schools.com](https://www.w3schools.com/html/default.asp), Mozilla's [MDN Docs](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web), Google's [Web.dev](https://web.dev) are also useful ressource for general documentation. Don't forget to **check the date** of the post/document (if it seems old, +5 years, check for more recent takes on your issue).

### 10 tips for a good bug report ([on testmonitor.com](https://www.testmonitor.com/blog/how-to-write-a-bug-report-that-solves-issues-effectively))

1. **Structure**: test carefully
2. **Reproduce**: test it again
3. **Isolate**: test it differently
4. **Generalize**: test it elsewhere
5. **Compare**: review results of similar tests
6. **Summarize**: relate test to customers
7. **Condense**: trim unnecessary information
8. **Disambiguate**: use clear words
9. **Neutralize**: express problem impartially
10. **Review**: be sure

### How to debug small programs (adapted from [Eric Clippert, read more here](https://ericlippert.com/2014/03/05/how-to-debug-small-programs/))

1. **Make sure the code runs**. If you are working with a language/framework that uses a compiler, there might be errors logs that can help. If working with JavaScript, add a `console.log('code runs');` or a `alert('code runs');` at various places within your code and check if your console displays the log or the alert pops. This will help identify where the code stops working. If working with CSS, add properties that can help you see the element's behavior (like `background-color:#00F;`).
2. **Break your code up into smaller methods**, each of which does exactly **one** logical operation.
3. **Summarize your method, technically**. By this, I mean, explain what is the goal of the method, how it achieves that goal, what inputs are expected / required, etc...
4. **Leave comments** inside your code on what happens and **write it in ways that are self-explanatory**. What does this do generally? And what each steps need to do in order for this to work? Use explicit variable names and function names that are self-explanatory. Use naming conventions in order to convey sense in what you write, like `camelCaseWriting` or `PascalCaseWriting` (for Javascript) or `snake_case_writing` or `kebab-case-writing` (for html/css). More on naming conventions on [betterprogramming.pub](https://betterprogramming.pub/string-case-styles-camel-pascal-snake-and-kebab-case-981407998841).
5. When you've defined your method, **make sure all preconditions for it to run are filled**: as an example, a function might not run because a variable required is undefined, because the element that provides this variable with its value fails to appear on your html page fails.
6. **Use if/else conditions** to find out where the bug might be (write *assertions*).
7. Make tests, **test each parts independently** in order to identify what doesn't.
8. **Use your browser's debugger** (!), Use the **web inspector tools**. Google Chrome -> [Shift]+[Cmd]+[C], or `View -> Developer Tools` | Firefox -> [Alt]+[Cmd]+[I], or `Tools -> Browser tools -> Web development tools`.
9. **Listen to your doubts**, and don't relinquish on **double-checking all aspects of the code**. Don't discard that the issue might be **something simple and obvious** (after the fact) that was in front of your eyes, that you couldn't see because you were too focused  thinking it was a complicated issue within a specific part.
10. If on mobile: run tests on your browser as well as a real device.
