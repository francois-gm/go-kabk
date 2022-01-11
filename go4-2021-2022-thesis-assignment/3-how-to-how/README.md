# How-to-how

Common issues

## Typos

Sometimes it doesn't work because there is a typo, and it can prove frustrating because one assumes the problem to be deeper and ends up being superficial.

### HTML

- Are your html tags opend <div> and closed </div>?
- Did you forget to close a tag?
- Some tags don't need to be closed, like <br>, <hr>, <img>...

### CSS

- Are brackets opened and **closed**
- Is the punctuation mark between your property and your value a colon, :, and is your punctuation mark after the value a semicolon, ; (as in color:blue;)

## Refresh issues, website doesn't appear with new changes (cache issues)

- Always test your website using your browser's '**private navigation**' mode, to make sure your browser's cache doesn't impact what you see. If your changes don't appear, close and re-open the browser and make sure you're in private mode. You can also append (add) ?ver=1.1 and increment this to your .css and .js stylesheets to force cache reload (to force other visitor's cache if you deploy your website again online). ([more](https://stackoverflow.com/questions/1614429/what-is-style-cssver-1-tag))
