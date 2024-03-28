# Notes: Bootstrap

<figure><img src="../.gitbook/assets/image (61).png" alt="" width="256"><figcaption><p>Bootstrap Logo</p></figcaption></figure>

### Web Development Frameworks

Developers use frameworks to improve efficiency and consistency and minimize error.  The Bootstrap framework provides components of CSS shorthand and HTML, CSS, and JavaScript.  We'll be using Bootstrap CSS shorthand for the project.  Working with HTML, CSS, and JavaScript in the browser classifies our work as front end.  This differentiates it from backend development, which involves writing code for a server instead of a browser.

Frameworks are constructive when you are working on multiple pages or a team.  As you learn the Bootstrap shorthand, think about how confusing it would be if every developer on a team created their own CSS shorthand or if every page used its own set of CSS class names.  Bootstrap creates its shorthand using classes.

### Bootstrap and CSS

Bootstrap is [well-documented](https://getbootstrap.com/docs/5.3/getting-started/introduction/).  Visit the documentation to learn how Bootstrap has created a shorthand for CSS.  We will link a local stylesheet containing Bootstrap's CSS to use it in the document.

```html
<link href="./css/styles.css" rel="stylesheet" />
```

#### Bootstrap Container Class

The `container` class is essential in Bootstrap for layout. It contains centers and pads  the elements it contains.  So, if a developer wants to layout items on a web page, they will likely turn to a `container` to do so.  You can use this class on every page and be confident that it means the same thing as long as every page links the same stylesheet.  The Bootstrap container is responsive and manages padding and margins across different device ranges.

```html
<div class="container">
  <!-- Content here -->
</div>
```

### Responsive Device Ranges

Bootstrap manages responsive pages using sizes like T-shirt sizes. The table below shows the cutoff points for each size. If the viewport is less than 575px, it is considered very small. After that, the cutoff points for viewports are designated by the minimum value of the range. So, a small device is between 576px and 765px, and a Medium device is between 768px and 991px. &#x20;

It helps to picture mobile devices like a cell phone as X-Small and a tablet as Small.  After that, the sizes refer to laptops and desktop monitors of different sizes.

<table><thead><tr><th width="140">X-Small</th><th width="92">Small</th><th>Medium</th><th width="93">Large</th><th>X-Large</th><th>XX-Large</th></tr></thead><tbody><tr><td>up to 575px</td><td>576px</td><td>768px</td><td>992px</td><td>1200px</td><td> 1400px</td></tr></tbody></table>

The code below shows a series of containers that will adjust their sizes at different breakpoints.

```
<div class="container-sm">100% wide until small breakpoint</div>
<div class="container-md">100% wide until medium breakpoint</div>
<div class="container-lg">100% wide until large breakpoint</div>
<div class="container-xl">100% wide until extra-large breakpoint</div>
<div class="container-xxl">100% wide until extra extra large breakpoint</div>
```

The container class works with the `row` and `col` classes to implement responsive flexbox layouts.  The `col` class also uses the sizing values used by the container class.

Here is an example of the implementation of a FlexBox layout using Bootstrap.  We'll look at the meaning of `gx` and `p` shortly.  Notice that the two `col` elements are children of the element with the `row` class, and the elements of the `row` class are children of the `container` element.

```html
<div class="container px-4 text-center">
  <div class="row gx-5">
    <div class="col">
     <div class="p-3">Custom column padding</div>
    </div>
    <div class="col">
      <div class="p-3">Custom column padding</div>
    </div>
  </div>
</div>
```

The above code can be found in the [bootstrap documentation](https://getbootstrap.com/docs/5.3/layout/gutters/#horizontal-gutters), showing you what it renders.

### Layout with  the Bootstrap Grid System

We've looked at the `container` class.  There is also a `container-fluid` class.  The difference is that the `container` class takes up a fixed page width, and the `container-fluid` class takes up the entire page width.

The **Grid System** that containers define is a twelve-column grid that essentially breaks up the width of the page into 12 units.  Element are laid out across these units.  An HTML element may take up as little as 1 unit of the container's width or up to 12 units of the container.  The columns are children of rows, so each row can be a container of a set of cols that each takes up 1 or more grid units. &#x20;

The image below shows many ways to layout elements across a 12-unit grid.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Bootstrap 12 unit Grid</p></figcaption></figure>

The code for the image above shows how this grid could be implemented.

```html
<div class="container-fluid">
        <div class="row">
            <div class="col-sm-1">1</div>
            <div class="col-sm-1">2</div>
            <div class="col-sm-1">3</div>
            <div class="col-sm-1">4</div>
            <div class="col-sm-1">5</div>
            <div class="col-sm-1">6</div>
            <div class="col-sm-1">7</div>
            <div class="col-sm-1">8</div>
            <div class="col-sm-1">9</div>
            <div class="col-sm-1">10</div>
            <div class="col-sm-1">11</div>
            <div class="col-sm-1">12</div>
        </div>
        <div class="row">
            <div class="col-sm-2">1</div>
            <div class="col-sm-2">2</div>
            <div class="col-sm-2">3</div>
            <div class="col-sm-2">4</div>
            <div class="col-sm-2">5</div>
            <div class="col-sm-2">6</div>
        </div>
        <div class="row">
            <div class="col-sm-3">1</div>
            <div class="col-sm-3">2</div>
            <div class="col-sm-3">3</div>
            <div class="col-sm-3">4</div>
        </div>
        <div class="row">
            <div class="col-sm-4">1</div>
            <div class="col-sm-4">2</div>
            <div class="col-sm-4">3</div>
        </div>
        <div class="row">
            <div class="col-sm-6">1</div>
            <div class="col-sm-6">2</div>
        </div>
        <div class="row">
            <div class="col-sm-12">1</div>
        </div>
        <div class="row">
            <div class="col-sm-4">1</div>
            <div class="col-sm-8">2</div>
        </div>
        <div class="row">
            <div class="col-sm-3">1</div>
            <div class="col-sm-6">2</div>
            <div class="col-sm-3">3</div>
        </div>
    </div>
```



### Summary of Bootstrap Classes

The table below summarizes the Bootstrap classes we'll encounter in the starter project.



<table><thead><tr><th width="172">Category</th><th width="210">Class Sample</th><th>Notes</th></tr></thead><tbody><tr><td><a href="https://getbootstrap.com/docs/5.3/layout/grid/">Grid System</a></td><td></td><td></td></tr><tr><td></td><td><code>container</code>, <code>container-fluid</code></td><td>Use <code>container</code> for fixed width and <code>container-fluid</code> for full width.</td></tr><tr><td></td><td><code>col</code>, <code>col-6</code>, c<code>ol-sm-6</code>, <code>col-auto</code></td><td>Use col to specify columns in the grid.  Use .col and .col-* for all device sizes.  Use size  (1-12) for responsive changes to column size.  Use a number to create a proportional width where all the numbers add up to 12 in a row.</td></tr><tr><td></td><td><code>row</code> <code>gx-4</code> or <code>gy-4</code></td><td>Add gutters to a row. They create horizontal padding with <code>gx</code> and vertical padding with <code>gy</code>.</td></tr><tr><td></td><td><code>row</code></td><td>The <code>row</code> elements contain the col elements.  Specify the gutter in the <code>row</code> element.</td></tr><tr><td></td><td><code>row-cols-2</code></td><td>Set the the number of rows in a column. Use just <code>col</code> for each column. In this example, there are 2 columns for each row.</td></tr><tr><td><a href="https://getbootstrap.com/docs/5.3/components/navbar">Nav</a></td><td></td><td></td></tr><tr><td></td><td><code>active</code></td><td>The <code>active</code> class will highlight the link in the navbar corresponding to the current page.</td></tr><tr><td></td><td><code>disabled</code></td><td>The <code>disabled</code> class will render the link unclickable and gray out the color.</td></tr><tr><td></td><td><code>navbar</code></td><td>The <code>navbar</code> provides a container for branding, responsive collapse, and wraps navigation links.</td></tr><tr><td></td><td>navbar-brand</td><td>Use navbar-brand to style the brand link in the upper left corner.</td></tr><tr><td></td><td><code>navbar-expand-lg</code>, <code>navbard-expand-md</code></td><td>Use <code>navbar-expand</code> with a size to enable responsive collapse of the <code>navbar</code>.</td></tr><tr><td></td><td><code>navbar-nav</code></td><td>Use <code>navbar-nav</code> to provide full height for navigation item wrapper.</td></tr><tr><td></td><td><code>navbar-toggler</code></td><td>Use navbar-toggler for responsive menu collapse.</td></tr><tr><td></td><td><code>navbar-toggler-icon</code></td><td>The navbar-toggler-icon is, by default, an image comprising 3 short horizontal lines and is sometimes called a "hamburger".</td></tr><tr><td></td><td><code>nav-item</code></td><td>The <code>nav-item</code> is applied to the block element that contains the link.</td></tr><tr><td></td><td><code>nav-link</code></td><td>The nav-link is the clickable element, usually an anchor tag that routes the user.  It can be assigned the <code>active</code> or <code>disabled</code> class.</td></tr><tr><td><a href="https://getbootstrap.com/docs/5.3/components/card">Card</a></td><td></td><td></td></tr><tr><td></td><td><code>card</code></td><td>The card is a versatile container that can contain text and images. By default, it does not have a margin.</td></tr><tr><td></td><td><code>card-body</code></td><td>The <code>card-body</code> is a container for the card title, card text, and buttons. These are optional. An image can be placed above the card body.</td></tr><tr><td></td><td><code>card-footer</code></td><td>Place the <code>card footer</code> below the card body in a block element.</td></tr><tr><td></td><td><code>card-title</code></td><td>The <code>card-title</code> is usually a header element.</td></tr><tr><td></td><td><code>card-text</code></td><td>The <code>card-text</code> is usually a paragraph element.  If there is a button, it often follows the text as a call to action.  The button can be an anchor tag style with <code>button</code>.</td></tr><tr><td><a href="https://getbootstrap.com/docs/5.3/utilities">Utilties</a></td><td></td><td></td></tr><tr><td></td><td><code>b</code>, <code>b-top</code>, <code>b-top-0</code>,  <code>b-bottom</code>, <code>b-start</code>, <code>b-end</code></td><td>Borders are added to all sides with <code>b</code>, or called out by position <code>top</code>, <code>bottom</code>, <code>start</code> (left), <code>end</code> (right). Adding a <code>-0</code> will remove a border.</td></tr><tr><td></td><td><code>fst-italic</code>, <code>fst-normal</code></td><td>Font style is added to provide italics or remove them</td></tr><tr><td></td><td><code>fw-bold</code>, <code>fw-normal</code></td><td>Font weight is used to make text bold.  There is a range of weights moving from the most to the least bold:  <code>bold</code>, <code>bolder</code>, <code>semi-bold</code>, <code>medium</code>, <code>normal</code>.</td></tr><tr><td></td><td><code>h-25</code>, <code>h-auto</code></td><td>Set height relative to a parent where <code>h-25</code> translates to 25% of the parent's height, and values can range from 0-100 or <code>auto</code>.</td></tr><tr><td></td><td><code>lh-base</code>, <code>lh-small, lh-large</code></td><td>Line height is controlled by sizes that expand the space between text in a paragraph or other block element.</td></tr><tr><td></td><td><code>mt-2</code>, <code>px-1</code></td><td>The mt-2 will set a margin of 50%  of a $spacer on the top of the element. The $spacer variable is 1rem by default.  A rem is the font size of the root element, which is usually 16px.  The px-1 will set padding 25% $spacer.   See the <a href="https://getbootstrap.com/docs/5.3/utilities/spacing/#margin-and-padding">documentation</a> for all values available.</td></tr><tr><td></td><td><code>text-start</code>, <code>text-center</code>, <code>text-end</code>, <code>text-lg-start</code></td><td>Text alignment provides <code>start</code>, <code>center</code>, and <code>end</code> as well as size for responsive alignment.</td></tr><tr><td></td><td><code>w-25</code></td><td>Set the width relative to the parent. This is the same method as height where the default values are <code>25%</code>, <code>50%</code>, <code>75%</code>, <code>100%</code>, and <code>auto</code>.</td></tr></tbody></table>

###



### StartBootstrap Templates

The Start Bootstrap Templates&#x20;

### StartBootstrap Small Business Starter



