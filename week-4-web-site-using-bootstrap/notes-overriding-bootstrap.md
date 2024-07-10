# Notes: Overriding Bootstrap

You can override Bootstrap CSS by creating your own CSS file and adding it to the `<head>` section of your web page.  If you have imported the Bootstrap styles in the head section, add your new `custom.css` file after the Bootstrap file or import.  The most recent CSS style will be the style. &#x20;

Here's how you write code to add the `custom.css` file to HTML:

```markup
  <!-- Core theme CSS (includes Bootstrap)-->
    <link href="css/styles.css" rel="stylesheet" />
  <!-- Custom CSS may override Bootstrap-->
   <link href="css/custom.css" rel="stylesheet" />
```

You can even use the same style name as Bootstrap in your custom file, which will replace the style. &#x20;

For example, Bootstrap is specifying that all of the HTML head tags should styled according to  these rules:&#x20;

```css
h6, .h6, h5, .h5, h4, .h4, h3, .h3, h2, .h2, h1, .h1 {
  margin-top: 0;
  margin-bottom: 0.5rem;
  font-weight: 500;
  line-height: 1.2;
}
```

If the design requires that `h1` headers have a larger margin-bottom, you can add this to your customer.css file:

```css
h1, .h1 {
  margin-bottom: 1.0rem;
}
```
