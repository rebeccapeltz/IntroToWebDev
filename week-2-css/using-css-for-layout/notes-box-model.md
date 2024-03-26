# Notes: Box Model

### Introduction to the Box Model

The Box Model looks at content and these CSS properties that determine how elements will be rendered concerning their neighbors and the page.

* padding
* borders
* margins
* height
* width

Every element defines a box. The box's inner and outer portions can be styled with padding and margin. There may also be a border on the box. By default, the content defines the width and height; if there is a border, it adds to this. This is inconvenient, so you will find it `box-sizing: border-box` added to many websites. This will tell the browser to include the border when calculating the width and height of the content. See [MDN Box Sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing) for more on this. You can see that there could be a problem specifying `width: 100%` and expecting that the content and border would be included in the element's box.

You'll also see that many stylesheets set the margin and padding to 0. This is because they are not 0 in all browsers. This process of "resetting" styles is called "normalizing." A web page may be viewed in many browsers and devices, and starting with the same default styles is essential.

The box model allows for two elements: block and inline. Block elements are characterized by disrupting the flow of content so that you get a new line whenever you use one. Inline elements can appear together on a line, and they don't disrupt the flow of content.

Block elements may have top and bottom margins, but inline elements don't because that would disrupt the flow of content.

You can assign height to a block element but not an inline element.

It is possible to make an inline element  `button` behave as a block element by using the `display: inline-block` property/value. This allows you to assign height to a button. Another use case  `inline-block` is to make a list appear horizontally. The `li` is a block item and renders vertically by default. In a navigation header, the list may need to be rendered horizontally and it `inline-block` can be used for this. This blog from [CSS Tricks](https://css-tricks.com/when-do-you-use-inline-block/) describes some use cases for this.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>CSS Box Model</p></figcaption></figure>

### Sample Code

The HTML divs will render on different lines because they are block elements.  In this example, the border is made up of 50px dots.  An inline span element demonstrates how it flows within the parent div element. The dimensions of this element are 210px wide by 160px high.&#x20;

```css
div {
  background-color: lightgrey;
  width: 100px;
  height: 50px;
  padding: 20px;
  margin: 20px;
}
```

```html
  <div>
    This is the text that makes up the 1st box.
  </div>
  <div>
    This is the text that makes up the 2nd box.
  </div>
```

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption><p>Box Model Shows Margin, Border, Padding and Content</p></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption><p>Two Divs with Margin and Padding</p></figcaption></figure>

Hover over one div in the browser to see how the space is allocated.  The tan color is the margin, and the green is the padding., and the blue is content.

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption><p>Chrome Inspector shows box model content, padding, and  margin</p></figcaption></figure>

### Block vs Inline: Margin and Padding

This example shows how margin and padding behave with block vs inline elements.  The block elements are outlined in green.  The inline element follows the second block element.  Notice in the image that the block element has a margin applied to the top, right, bottom, and left (both horizontal and vertical) directions.  The inline span element has a margin specified for the top and right, but it is only applied to the right (horizontal).  Padding is applied to all sides of each element.  For the block elements, it never overlaps, but for the inline element, it can overlap.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>Inline Element Top Padding causes Overlap</p></figcaption></figure>

### Centering Content on a Page Using Box Model

Box model techniques rely on padding, margin, width, and height.  In the code below, we create a style for a class named `container`.  The element assigned to this class could be a child of the `body` component or another aspect on the web page.  By setting the width to  80%, we nest the children within the container's parent because it will only take up a portion of the parent's width.

Setting the margin to auto is equivalent to setting `margin-right` and `margin-left` to auto.  This will center content horizontally within its parent.  Setting `text-align` to `center` will center all the block elements within the container.

```css
.container {
  width: 80%;
  margin: auto;
  text-align: center;
}
```

The code below demonstrates how to apply box model properties to achieve centered content.

```html
<head>
<style>
.container {
  width: 80%;
  margin: auto;
  text-align: center;
}
</style>
</head>

<body>
<div class="container">
    <h1>This Header is Centered</h1>
    <p>This element has is centered.</p>
</div>
</body>
```

The result is a page where the header and paragraph are both centered.

<figure><img src="../../.gitbook/assets/image (34).png" alt=""><figcaption><p>Centering Content using Box Model Properties</p></figcaption></figure>

### Resources

[MDN Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building\_blocks/The\_box\_model)
