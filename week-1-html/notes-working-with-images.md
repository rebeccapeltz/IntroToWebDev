# Notes: Working With Images

### Image Element

The image element uses the img tag to embed an image on a web page.  There are 2 required attributes:

* `src` is the path to the image and it can be a local path or a URL
* `alt` is the text displayed if the browser settings do not allow for rendering images or the path to the image doesn't return an image.

Images will render if the browser settings allow for it and the value supplied in `src` returns an image, but if they don't, the text supplied in the `alt` attribute will render instead.  In the example below, the src is pointing to a website that returns HTML an not text, so the alt attribute value is displayed instead.

```
<img src="http://www.wikipedia.com" alt="Dog Barking" >
```

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>The alt attribute value is displayed when the image is not available or can't be rendered</p></figcaption></figure>

There are more attributes associated with the image tag.  We'll use the `height` and `width` attributes to solve a problem in the next section.

### Properties of Images and Aspect Ratio

The properties of images that web developers need to know to serve up the best-looking image are:

* The size is usually expressed as width x height in pixels
* The resolution determines the clarity of the image and is generally expressed in DPI, or "dots per inch."
* The metadata includes the filename, URL, and other data depending on the camera, like location, time, and date.

We'll focus on the size properties as these are important in layout.  A layout design will often specify the size of the image in terms of width and height.  The original image may be much larger than the design specifies.  Also, the original image may not have the same aspect ratio as the image displayed on the web page. &#x20;

The HTML `img` element allows us to specify the height and width of the image, but we don't want to select a height and width that creates a different aspect ratio than the original image, or the image will appear skewed.

Let's say our design looks like this, and we need an image with a width of 600px and a height of 400px. &#x20;

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption><p>Design showing image with 600x400 Dimension</p></figcaption></figure>

We can set the height and width of any image to these values in the image tag, but if we don't maintain the aspect ratio, the image will look skewed.  The original dimensions of this image are 5759 x 6930.  The height is larger than the width, yet we are telling the browser to render at 600 x 400 where the width is greater than the height.  The effect of skewing is to see the image "stretched" in on e of the dimensions, in this case width.

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption><p>Skewed Image</p></figcaption></figure>

The actual image looks like this.

<figure><img src="../.gitbook/assets/image (23).png" alt="" width="360"><figcaption><p>Image Rendered with Original Dimensions</p></figcaption></figure>

How can we resolve this problem? The easiest way is to set the image height to the design height, 400px, and the width to "auto." The image will not fill the space, but it will retain its aspect ratio.

```html
<img height="400" width="auto" src="./tree.jpg"/>
```

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption><p>Set Height to 400px and Width to Auto to Retain Aspect Ratio</p></figcaption></figure>

We'll see more ways to work with images.  Cropping an image to a desired height will fix the problem.  You can use tools like Preview on the Mac and the Photos app on Windows 11 to crop images.  There are also online solutions like [Cloudinary](https://cloudinary.com/) that can help with image cropping.

### How to get Free Images

We'll be using images in our projects.  You can use your photos, but accessing free photos online is helpful if you want to collect various pictures on a given subject.   Here are three websites that will allow you to download pictures and use them without charge:

* [Pexels](https://www.pexels.com/)
* [Unsplash](https://unsplash.com/)
* [Pixabay](https://pixabay.com/)

If you are a photographer, you can upload your images to these websites and share your photos with others there.

During development, when you want to focus on coding HTML and CSS, you can use an image service that provides random images in the dimensions you need for your page design.  Try [Lorem Picsum](https://picsum.photos/).  With Lorem Picsum, you add the width and height in the URL to get the exact dimensions you need.  For example, if you need a 600 x 400 image, you would use this URL for the `src` attribute.

`https://picsum.photos/600/400`

<figure><img src="https://picsum.photos/600/400" alt=""><figcaption><p>Random 600 x 400 Image from Lorem Picsum</p></figcaption></figure>

The term "Lorem Picsum" is a take-off from the term "Lorem Ipsum".   This term refers to placeholder text and is used by designers and developers when they need to fill up a certain space on a web page with text.  There are many Lorem Ipsum generators.  Look at [https://loremipsum.io/](https://loremipsum.io/) to learn more about placeholder text and how to generate it.

#### Placeholder Images

If you just want to fill up a particular dimension, look at  [Fake Images Please](https://fakeimg.pl/).

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Using Fake Images Please: <a href="https://fakeimg.pl/600x400">https://fakeimg.pl/600x400</a></p></figcaption></figure>

### Compressing Images



### Uploading Images to Replit



### Setting Up the Image Src Attribute



### Resources

[W3C Image Tag](https://www.w3schools.com/tags/tag\_img.asp)
