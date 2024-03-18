# Notes: Flexbox

### Introduction to Flexbox

Flexbox is a one-dimensional model that only deals with one dimension at a time: row or column. However, it often produces two-dimensional layouts because it has a wrap property that allows elements to wrap around, giving the appearance of multiple rows or columns.

To use Flexbox, we need to apply the following properties

* Set parent container to `display: flex`
* Set `flex-direction` to column or row:  `flex-direction: column | row`
* Use `justify-content` To distribute children along the primary axis: `justify-content: center`
* Use `align-items` To distribute children along the cross-axis: `align-items: center`

<table><thead><tr><th width="156">Flex Direction</th><th>Primary Axis: justify-content</th><th>Cross-Axis: align-items</th></tr></thead><tbody><tr><td>Column</td><td>Vertical</td><td>Horizontal</td></tr><tr><td>Row</td><td>Horizontal</td><td>Verticl</td></tr><tr><td></td><td></td><td></td></tr></tbody></table>

### Flex Row Example

Items are laid out by row and are centered across the row using `justify-content.`

```html
<head>
<style>
.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  background-color: blue;
}

.container > div {
  background-color: lightgrey;
  margin: 10px;
  padding: 20px;
  font-size: 30px;
  width: 55px;
  text-align: center;
}
</style>
</head>
<body>

<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>  
</div>
</body>
```

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption><p>Row Flex with JustifyContent Center</p></figcaption></figure>

### Column Flex Example

Items are laid out by column and are centered across the row using `align-items.`

```
<head>
<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: blue;
}

.container > div {
  background-color: lightgrey;
  margin: 10px;
  padding: 20px;
  font-size: 30px;
  width: 55px;
  text-align: center;
}
</style>
</head>
<body>

<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>  
</div>
</body>
```

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption><p>Flex Direction Column and Item Aligned to Center Within Row</p></figcaption></figure>

### Flex Box Wrap

The ability for this one-dimensional layout to wrap is what makes this a good choice for Responsive websites.  In the code below, we have set up a centered, row wrap.

```html
<head>
<style> 
#container {
  width: 80%;
  border: 1px solid #c3c3c3;
  padding: 5px;
  display: flex;
  justify-content: center;
  flex-direction: row;
  flex-wrap: wrap;
}

#container div {
  width: 300px;
  height: 200px;
}
</style>
</head>

<body>
<div id="container">
  <div style="background-color:coral;">A</div>
  <div style="background-color:lightblue;">B</div>
  <div style="background-color:khaki;">C</div>
  <div style="background-color:pink;">D</div>
</div>
</body>
```

The result on a screen wider than 600 px is shown below.

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption><p>Row Wrap 600px Wide Divs</p></figcaption></figure>

The result on a screen less than 600px is this:&#x20;

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption><p>Row wrap on screen less than 600px</p></figcaption></figure>

This ability to spread content on a larger screen and contract to a single row on a smaller screen makes Flex so helpful when creating responsive web pages.

### Centering Content on a Page Using FlexBox

To center the elements on a page using FlexBox, we use the flex-direction:column to line up the element in a column.  The align-items property lines up elements on the cross-axis, so horizontally.

The code below demonstrates how to apply box model properties to achieve centered content.

```html
<head>
<style>
.container {
    display: flex;
    flex-direction: column;
    align-items:center;
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

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Centering Content with FlexBox</p></figcaption></figure>

### Resources

[MDN Basic Concepts of Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_flexible\_box\_layout/Basic\_concepts\_of\_flexbox)

