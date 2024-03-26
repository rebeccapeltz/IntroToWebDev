# Notes: CSS

CSS is an acronym for **Cascading Style Sheets**

This week, we start working with CSS. CSS is a declarative language that instructs the browser how to apply style to sections of an HTML web page. Style can include color, positioning, fonts, and animation.

We'll start learning to center the contents of a web page so that it is not all bunched up at the left of the page. Then, we'll look at laying out images for an image gallery. This layout could be achieved in many ways, but we'll be learning to use the [Flex Box](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) layout.

### Selectors and Properties

CSS code is made up of **Selectors** and **Properties**. It follows this pattern:

```css
selector {
    property: value;
}
```

Selectors can be HTML tags, HTML ID attributes, or CSS classes.  &#x20;

#### Element Tag Selector

In the example below, an HTML tag is used as a selector.  It sets the color of the paragraph text to black.

```css
/* Tag Selector */
p {
    color: #000;
}
```

#### Class Selector

In the example below, we show HTML and CSS.  The HTML div element has a class attribute.  Classes may be applied to many elements on a page.  CSS will attempt to style all classes as defined in the code.  Both paragraphs 1 and 3 will have a blue font color because they have been assigned the `brand` class.&#x20;

```html
<p class="brand">This is paragraph 1.</p>
<p>This is paragraph 2.</p>
<p class="brand">This is paragraph 3.</p>
```

```css
/* class Selector */
.brand {
    color: blue;
}
```

#### Element ID Selector

In the example below, we show HTML and CSS.  The HTML div element has an ID attribute set to "container".   The CSS uses the ID attribute as a selector.  The `#` is used to indicate a container.  IDs are unique on a page, so this method is more specific than using a `div` for a selector.

```html
<div id="container">
Hello
</div>
```

```css
/* id selector */
#container {
    background-color: grey;
}
```



### Three Ways to Add CSS to a Web Page

There are 3 ways to add CSS to a web page:

1. Create a separate file containing CSS and link it to the web page using the `link` HTML tag. In the example below, we would place the `link` tag in the `head` section of the document.  The file `style.css` would be located in the same directory as the HTML file containing the link tag.

{% code fullWidth="false" %}
```html
<link href="style.css" rel="stylesheet" type="text/css" />
```
{% endcode %}

2. Create a `<style>` section in the `head` section of an HTML page and add CSS that will be applied to the page.

```
<style>
    body{
        color: red;
        background-color: white;
        font-size: 1rem;
    }
</style> 
```

3. Add `style=""` attributes to an HTML element tag and style the element directly. In the example below, we are styling the color of the paragraph text to be light grey and the background color black.  No selectors are needed when assigning properties to an element using the style attribute.

```
<p style="color: lightgrey;background-color:black;">Hello</p>
```

Developers have often coded the CSS in separate files and linked it to the web page. This allows for the reuse of CSS across many pages. However the closer the CSS code is to the HTML that is is styling, the more likely it will be applied. See the section on "Cascading" to learn more about this.

### Cascading, Specificity, and Inheritance Rules

**Cascading** in the CSS acronym refers to browsers' methods to resolve conflicts when different styles refer to the same elements. Because there are multiple ways that styles can be added, such as linking to external documents, using the \
&#x20;tag, and using inline styles, there has to be a way to resolve which gets used. You can usually determine the style used by finding the one closest to the element. An inline style would be applied over a style provided in a linked stylesheet.  Cascade rules look at the order of the styles as they apply to an element.

In the example below, the "Gill Sans, sans-serif" font family will be used for all paragraphs because it was specified after the "George, serif". CSS rules interpret styles that are lower in the list as closer to the item styles.&#x20;

```
p {
    font-family: Georgia, serif;
}
p {
    font-family: Gill Sans, sans-serif;
}
```

**Specificity** refers to the "cascade" used to evaluate an element's style. In the example above, both styles used the same cascade layer. They both provide styles applied to a paragraph. The ID selector is the most specific in the examples above, followed by the class and element selectors.

**Inheritance** refers to CSS applying styles to elements contained within another styled element.  In the example below, the body is styled to use a sans-serif font family.  This means that all elements within the body will use sans-serif.   We can override inheritance by using a more specific style.

The main header and the first paragraph are rendered as sans-serif, but the second paragraph is expressly set to render as serif. So, the first paragraph inherits from the body style, but the second paragraph uses a more specific style and does not use inheritance for the font family.

In this example, we see using both tag and class to create a selector. `p.discussion`.

```css
body {
  font-family: Gill Sans, sans-serif;
}
p.discussion {
   font-family: Georgia, serif;
}
```

```html
<body>
    <h1>Header 1</h1>
    <p>First is a paragraph rendered sans-serif.</p>
    <p class="discussion">This paragraph is rendered with the serif font.</p>
</body>

```

###

### HTML Elements: Block and Inline Elements

Block Elements have the following characteristics when rendered on a web page:

* they always start on a new line
* they use an entire line
* both height and width properties can be applied
* both vertical and horizontal margins can be applied
* padding works on all sides

Inline Elements have the following characteristics when rendered on a web page:

* do not start on a new line unless directly following a block element
* width is determined only by the size of the content
* height and width properties cannot be applied
* horizontal margin can be applied, but a vertical margin cannot
* padding works on all sides but may overlap

In general, block elements provide a page's structure, and inline elements format content within a block.

Sometimes, we want to override some of the built-in behavior of block and inline elements. Using the `<br>` element is an example of adding a new line after an inline element.  The \<br> element is a  The Image element is inline.  If two image elements are side by side, they will render on the same line.  Using the \<br> we force the next element to the next line.

```html
<!-- dog and cat render next to each other on the same line  -->
<img src="dog.jpg"><img src="cat.jpg">
```

```
<!-- dog and cat render on separate lines -->
<img src="dog.jpg"><br>
<img src="cat.jpg">
```

Another way to solve the problem above is to wrap the image elements in a block element like a `<div>`.

```html
<!-- wrap images in a div tag -->
<div>
<img src="dog.jpg">
</div>
<div>
<img src="cat.jpg">
</div>
```

### CSS Solutions for Block and Inline Elements

We can use CSS instead of HTML to solve the problem above with images.  Here is the HTML and CSS that uses the `display` property to make images behave as block elements.  Images are a little different than other inline elements in that you can set their height or width, but by using the display property, you can guarantee they will render on separate lines.

```
<!-- dog and cat render on separate lines  -->
<img style="display:block;" src="dog.jpg">
<img style="display:block;" src="cat.jpg">
```

Another use for `display` is to make anchor tags, which are inline, render horizontally as anchor tags normally would, but give them a height and width.  We know that height and width are usually only available for block element.  This is commonly see in a navigation bar.

In the CSS below, we are setting the `nav a` to `display inline-block`. Note that we using specificity so that only the anchor elements under the nav element use this code.  Once the elements are set to `inline-block` we can apply height and width.  The rest of the properties can be applied to inline or block elements.  The result is shown below.

```css
nav a {
    display: inline-block;
    height: 20px;
    width: 100px;
    background-color: #000;
    color: lightgrey;
    font-family: sans-serif;
    text-align: center;
    text-decoration: none;
    cursor: pointer;
}
```

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### HTML Tags are Categorized by Block and Inline

#### Block Elements

* address
* article
* aside
* audio
* blockquote
* canvas
* dd
* div
* dl
* dt
* fieldset
* figcaption
* figure
* footer
* form
* h1-h6
* header
* hr
* li
* main
* nav
* noscript
* ol
* p
* pre
* section
* table
* thead
* tfoot
* ul
* video

#### Inline Elements

* a
* abbr
* acronym
* b
* bdo
* big
* br
* buttom
* cite
* code
* dfn
* em
* i
* img
* input
* kbd
* label
* map
* object
* output
* q
* samp
* script
* select
* small
* span
* strong
* sub
* sup
* textarea
* time
* tt
* var



### Color in CSS

Color can be expressed in many ways in CSS. It is a value for the `color` and `background-color` properties. CSS provides `16,777,216` colors. This is based on 256 colors per each of the Red/Green/Blue. Multiply `256 * 256 * 256` to get `16,777,216`.\
RGB colors are expressed as hex values. Hex values are base 16 values (0,1,2,3,4,5,6,7,8,9, A, B, C, D, E, F). The color white, which is all RGB channels turned to their highest value is `FFFFFF` , and you will see it in code often abbreviated as `#FFF`. The color black, which is all RGB channels turned off, is expressed as, abbreviated as `#000`. The color red is `#F00` or `#FF0000` because the 1st channel is red. The color green is `#0F0` or `#00FF00` because the 2nd channel is green. and the color blue is `#00F` or `#0000FF` because the 3rd channel is blue.\
You can express colors by their names, but there aren't 16 million names for colors, the RGB is more expressive. This [Wikipedia Color Chart](https://en.wikipedia.org/wiki/Web\_colors) shows many named colors with their RGB values. The chart also shows HSL and HSV conventions for specifying colors.

There may be color names not found on all browsers or devices, so if you want to use a color with a less well-known name, it's a good idea to use its RGB values. Colors like black, white, grey, red, blue, and green will not have a problem, but a color like "celadon" might not work and you could use `#ACDCAC` instead.

This [Color Picker](https://www.w3schools.com/colors/colors\_picker.asp) provides a good way to experiment with colors used on web pages.

In CSS, you set colors for text and background using these properties, where we set the text color to navy and the background color to silver.

```
color: navy;
background-color: silver;
```

or

```
color: #000080;
background-color: #C0C0C0
```

### Fonts in CSS



Text can be styled using Font Families and individual fonts. Browsers have default fonts, so if you don't provide a font or font family, you will see the default rendered. Browsers provide font families to specify multiple fonts so that the browser rendering the text will likely have the look that the developer is trying to achieve.

You can get an idea of what different fonts look like by looking at the different fonts on the Core Web Fonts.

Compare Arial to Georgia. You'll notice that Georgia has little hooks on many letters similar to what you would see in an old typewriter, while Arial does not have these hooks. The hooks are called "serifs." Fonts like Georgia are "serifs," and fonts like Arial are "sans serifs," where the term "sans" means "without."

In general, serif fonts are used for large amounts of text like those in a book or newspaper, while sans serif fonts are used in posters and web pages.

#### Sample Font Specification in CSS

Fonts can be specified using font families. In this example we create classes called 'serif' and 'sanserif' and then apply font families to paragraphs that use these classes. Notice that when using font families we provide a list of fonts for the browser to choose from. Because we are applying these style to classes, the selector starts with a `.`.

```
.serif {
    font-family: "Times New Roman", Times, serif;
}
.sans-serif {
    font-family: Arial, Helvetica, sans-serif;
}
```

```
<p class="serif">I am serif</p>
<p class="sans-serif">I am sans serif</p>
```

#### Safe Fonts

Because fonts can vary across browsers, there is a list of safe fonts that includes fonts that are likely to be found on every browser. See this of [Safe Fonts](https://www.w3schools.com/cssref/css\_websafe\_fonts.php).



### Resources



[W3 Schools CSS](https://www.w3schools.com/css/)

[Mozilla Development Network (MDN) CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)

[11 Ways to Center ...](https://blog.hubspot.com/website/center-div-css)
