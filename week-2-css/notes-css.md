# CSS Notes

CSS is an acronym for **Cascading Style Sheets**

This week, we start working with CSS. CSS is a declarative language. It instructs by telling the browser how to apply style to sections of an HTML web page. Style can include, color, positioning, fonts and animation.

We'll start learning centering the contents of a web page so that it is not all bunched up at the left of the page. Then we'll look at laying out images for an image gallery. There are many ways that this layout could be achieved but we'll be learning to use [Flex Box](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) layout to do this.

### Selectors and Properties



CSS code is made up of **Selectors** and **Properties**. It follows this pattern:

```
selector {
    property: value;
}
```

Selectors can be HTML tags, HTML id attributes, or CSS classes. There are 3 ways to add CSS to a web page:

1. Create a separate file containing CSS and link it to the web page using the `link` HTML tag.
2. Create a `<style>` section in the `<head>` of an HTML page and add CSS that will be applied to the page.
3. Add `style=""` attributes to an HTML element tag and style the element directly.

Traditionally, developers have coded the CSS in separate files and linked it to the web page. This allows for the reuse of CSS across many pages. However the closer the CSS code is to the HTML that is is styling, the more likely it will be applied. See the section on "Cascading" to learn more about this.

### CSS Selectors



This [MDN Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference) can help you to see the variety of properties that you can use in your CSS file.

The list below shows the properties we'll use in this week's assignment:

* `*` all elements
* `body`,`span`,`ul`, `li`, `img` are HTML elements and styles will be applied to all
* `.container`, `.heading-text` and many more are classes you can make up the names yourself and they are referenced by the `.` in front
* `#id` the `#` in front of a name indicates an element with a unique id that has been supplied as an attribute of the element

**something about "specificty" and how you can address child items**



### Box Model



Every element defines a box. There is an inner and outer portion of the box, and these spaces can be styled with padding and margin respectively. They may also be a border on the box. By default the content defines the width and height and if there is a border it adds to this. This is not convenient so you will find the `box-sizing: border-box` added to many websites. This will tell the browser to include the border in calculating the width and height of the content. See [MDN Box Sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing) for more on this. You can see that there could be a problem specifying `width: 100%` and expecting that the content and border would both be included in the elements box.

You'll also see that many stylesheets set margin and padding to 0. This is because they are not 0 in all browsers. This process of "resetting" styles is called "normalizing". A web page may be viewed in many browsers and devices and it's important to start with the same set of default styles.

The box model allows for two different types of elements: block and inline. Block elements are characterized by disrupting the flow of content so that you get a new line when ever you use one. Inline elements can appear together on a line and they don't disrupt the flow of content.

Block elements may have top and bottom margins, but inline elements don't because that would disrupt the flow of content.

You can assign height to a block element, but not to an inline element.

It is possible to make an inline element like `button` behave as a block element by using the `display: inline-block` property/value. This allows you to assign height to a button. Another use case for `inline-block` is to make a list appear horizontally. The `li` is a block item and renders vertically by default. In a navigation header, the list may need to render horizontally and the `inline-block` can be used for this. This blog from [CSS Tricks](https://css-tricks.com/when-do-you-use-inline-block/) describes some use cases for this.

[![](https://github.com/rebeccapeltz/introwd/raw/main/images/box-model.png)](https://github.com/rebeccapeltz/introwd/blob/main/images/box-model.png)

### HTML Elements Box and Inline



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

### The Meaning of "Cascading"



The term **Cascading** in CSS refers to the algorithm that browser use to resolve conflicts when different styles refer to the same elements. Because there are multiple ways that styles can be added such as linking to external documents, using the `style` tag, and inline styles, there has to be a way to resolve which actually gets used. In general you can usually determine the style that will be used by finding the one closest to the element. An inline style would be applied over a style provided in a linked stylesheet.\
You can read more about this at [MDN here](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade).

### Color in CSS



Color can be expressed in many ways in CSS. It is a value for the `color` and `background-color` properties. CSS provides `16,777,216` colors. This is based on 256 colors per each of the Red/Green/Blue. Multiply `256 * 256 * 256` to get `16,777,216`.\
RGB colors are expressed as hex values. Hex values are base 16 values (0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F). The color white which is all RGB channels turned to their highest value is `FFFFFF` and you will see it in code often abbreviated as `#FFF`. The color black which is all RGB channels turned off is expressed as `#000000`, abbreviated as `#000`. The color red it `#F00` or `#FF0000` because the 1st channel is red. The color green is `#0F0` or `#00FF00` because the 2nd channel is green. and the color blue is `#00F` or `#0000FF` because the 3rd channel is blue.\
You can express colors by their names, but there aren't 16 million names for colors, the RGB is more expressive. This [Wikipedia Color Chart](https://en.wikipedia.org/wiki/Web\_colors) shows many named colors with their RGB values. The chart also shows HSL and HSV conventions for specifying colors.

There may be color names that are not found on all browsers or devices, so if you want to use a color with a less well known name, it's a good idea to use its RGB values. Colors like black, white, gray, red, blue, green will have not have a problem, but a color like "celadon" might not work and you could use `#ACDCAC` instead.

This [Color Picker](https://www.w3schools.com/colors/colors\_picker.asp) provides a good way to experiment with colors used on web pages.

In CSS you set colors for text and background using these properties where we set the text color to navy and the background color to silver.

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



Text can be styled using Font Families and individual fonts. Browsers have default fonts, so if you don't provide a font or font family, you will see the default rendered. Browsers have provide font families as a way to specify multiple fonts so that the browser that is rendering the text will be likely to have the look that the developer is trying to achieve.

Look at the different fonts on the [Core Web Fonts](https://en.wikipedia.org/wiki/Core\_fonts\_for\_the\_Web) to get an idea of what different fonts look like.

Compare Arial to Georgia. You'll notice that Georgia has little hooks on many letters similiar to what you would see in an old typewriter, while Arial does not have these hooks. The hooks are called "serifs". Fonts like Georgia are "serif" and fonts like Arial are "sans serif", where the term "sans" means "without".

In general serif fonts are used for large amounts of text like you would see in a book or newspaper, while sans serif fonts are seen in posters and on web pages.

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



Because fonts can vary across browser, there is a list of safe fonts that includes fonts that are likely to be found on every browser. See this of [Safe Fonts](https://www.w3schools.com/cssref/css\_websafe\_fonts.php).

### Centering Items on a Web Page



### Resources



[W3 Schools CSS](https://www.w3schools.com/css/)

[Mozilla Development Network (MDN) CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)

[11 Ways to Center ...](https://blog.hubspot.com/website/center-div-css)
