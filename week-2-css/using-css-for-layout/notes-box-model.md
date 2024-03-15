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

### Resources

[MDN Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building\_blocks/The\_box\_model)
