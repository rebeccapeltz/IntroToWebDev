# Notes: Favicons

### Favicons

The term favicon is a contraction for "favorite icon".  In the head section of a web page, you can include a favicon which will show up next to the the title in the tab of the browser.  This is optional.  It is helpful to users who have mutliple tabs open in their browser.  Sometimes, the title is too long to see but a small icon can help locate the page.

Look at the head section of index.html to find the following code:

```html
  <!--use a small image for favicon-->
  <link rel="icon" type="image/png" href="(favicon image)" />
```

For the (favicon image), you can upload an icon and link to the uploaded file in your project.  An image of a browser tab showing the Wikipedia favicon is shown below. Notice that you can't see the whole word "Wikipedia", but you can clearly see the familiar "W" icon.

<figure><img src="../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

Right click on the web page, and select **View Source**. The source code for the web page will be diplayed as text.  Searching through the Wikipedia HTML source, you can find the code that loads the favion shown above.

```html
<link rel="icon" href="/static/favicon/wikipedia.ico">
```
