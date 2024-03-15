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

### Resources

[MDN Basic Concepts of Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_flexible\_box\_layout/Basic\_concepts\_of\_flexbox)

