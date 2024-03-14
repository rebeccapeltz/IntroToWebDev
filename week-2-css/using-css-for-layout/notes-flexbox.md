# Notes: Flexbox

### Introduction to Flexbox

Flexbox is a one-dimensional model in that it only deals with one dimension at a time: row or column. However, it often produces two-dimensional layouts because it has a wrap property that allows elements to wrap around, giving the appearance of multiple rows or columns.

Responsive Layouts

Responsive layouts are those that can work with different **viewport** sizes.  A viewport is the size of a phone, table, or screen used to view web pages.  These screens come in various sizes.

The table below summarizes the width and height of different device screens.  This is not a complete list.

| Device  | Width  | Height |
| ------- | ------ | ------ |
| Laptop  | 1440px | 900px  |
| Tablet  | 1776px | 1024px |
| Desktop | 1920px | 1080px |

When we create layouts, we have to consider how they would appear on another device. On a laptop, we could show four images across, but on a mobile device, we could only show one image per row.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Flex Box Row Wrap</p></figcaption></figure>

The Chrome browser has tools to help see what a web page would look like on different devices. To activate the Responsive layout, open the Inspector and then click on "Toggle Device Toolbar".

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>How the Image Gallery Looks on a Mobile Device </p></figcaption></figure>

### Code for Row Wrap

In this example, the images and titles are coded in HTML, and the items are contained in an unordered list.  The `ul` `list-style` is set to none to remove the bullet points that are rendered by default for list items.

```html
 <ul class="image-gallery">
     <li>
        <img src="./images/rw1.jpeg" alt="" />
        <div class="image-title"><span>Image title</span></div>
      </li>
      <li>
        <img src="./images/rw2.jpeg" alt="" />
        <div class="image-title"><span>Image title</span></div>
      </li>
      <li>
        <img src="./images/rw3.jpeg" alt="" />
        <div class="image-title"><span>Image title</span></div>
      </li>
      <li>
        <img src="./images/rw4.jpeg" alt="" />
        <div class="image-title"><span>Image title</span></div>
      </li>
      <li>
        <img src="./images/rw5.jpeg" alt="" />
        <div class="image-title"><span>Image title</span></div>
      </li>
      <li>
        <img src="./images/rw6.jpeg" alt="" />
        <div class="image-title"><span>Image title</span></div>
      </li>
      <li>
        <img src="./images/rw7.jpeg" alt="" />
        <div class="image-title"><span>Image title</span></div>
      </li>
      <li>
        <img src="./images/rw8.jpeg" alt="" />
        <div class="image-title"><span>Image title</span></div>
      </li>
      <li>
        <img src="./images/cookie1.avif" alt="" />
        <div class="image-title"><span>Image title</span></div>
      </li>
 </ul>
```

```css
ul {
  list-style: none;
}
.image-gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
}
```

### Code for Column Wrap

In this example, the images and titles are coded using div containers. There are 3 column containers containing 3 images and their titles, for a total of 9 images. It's good to look at this code and identify the pattern because it is repetitious.  Once we see the pattern, it will help us use this code.

```html
 <div class="image-gallery">
     <div class="column">
        <div class="image-item">
            <img src="./images/1.jpg" alt="" />
            <div class="overlay"><span>Image title</span></div>
        </div>
        <div class="image-item">
            <img src="./images/cookie1.avif" alt="" />
            <div class="overlay"><span>Image title</span></div>
        </div>
        <div class="image-item">
            <img src="./images/2.jpg" alt="" />
            <div class="overlay"><span>Image title</span></div>
        </div>   
    </div>
    <div class="column">
        <div class="image-item">
            <img src="./images/3.jpg" alt="" />
            <div class="overlay"><span>Image title</span></div>
        </div>
        <div class="image-item">
            <img src="./images/cookie5.avif" alt="" />
            <div class="overlay"><span>Image title</span></div>
        </div>
        <div class="image-item">
            <img src="./images/4.jpg" alt="" />
            <div class="overlay"><span>Image title</span></div>
        </div>
    </div>
    <div class="column">
        <div class="image-item">
            <img src="./images/5.jpg" alt="" />
            <div class="overlay"><span>Image title</span></div>
        </div>
        <div class="image-item">
            <img src="./images/cookie6.avif" alt="" />
            <div class="overlay"><span>Image title</span></div>
        </div>
        <div class="image-item">
            <img src="./images/6.jpg" alt="" />
            <div class="overlay"><span>Image title</span></div>
        </div>
    </div>
<div>
```

We can view the pattern schematically.

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

### Resources

[MDN Basic Concepts of Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_flexible\_box\_layout/Basic\_concepts\_of\_flexbox)

