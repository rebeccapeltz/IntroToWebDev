# Notes: Box Model

Every element defines a box. An inner and outer portion of the box can be styled with padding and margin, respectively. There may also be a border on the box. By default, the content defines the width and height; if there is a border, it adds to this. This is inconvenient, so you will find it `box-sizing: border-box` added to many websites. This will tell the browser to include the border when calculating the width and height of the content. See [MDN Box Sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing) for more on this. You can see that there could be a problem specifying `width: 100%` and expecting that the content and border would be included in the element's box.

You'll also see that many stylesheets set the margin and padding to 0. This is because they are not 0 in all browsers. This process of "resetting" styles is called "normalizing." A web page may be viewed in many browsers and devices, and starting with the same default styles is essential.

The box model allows for two elements: block and inline. Block elements are characterized by disrupting the flow of content so that you get a new line whenever you use one. Inline elements can appear together on a line, and they don't disrupt the flow of content.

Block elements may have top and bottom margins, but inline elements don't because that would disrupt the flow of content.

You can assign height to a block element but not an inline element.

It is possible to make an inline element  `button` behave as a block element by using the `display: inline-block` property/value. This allows you to assign height to a button. Another use case  `inline-block` is to make a list appear horizontally. The `li` is a block item and renders vertically by default. In a navigation header, the list may need to be rendered horizontally and it `inline-block` can be used for this. This blog from [CSS Tricks](https://css-tricks.com/when-do-you-use-inline-block/) describes some use cases for this.

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p>CSS Box Model</p></figcaption></figure>

