# Project: Bootstrap Website

<figure><img src="../.gitbook/assets/schematic.png" alt=""><figcaption><p>Schematic of Get Bootstrap Small Business Template from Start Bootstrap</p></figcaption></figure>

### StartBootstrap Small Business Starter

Adding features and content to an existing project starts with understanding the existing code.  The key is to look for patterns in the code and recognize what they are rendering. Drawing a schematic diagram like the one above that captures the patterns on the index page of the Small Business starter helps to see the code patterns.

The page starts with a nav bar containing links to other pages. Then comes the heading row, which includes an image lined up with three rows of header, paragraph, and call-to-action button (CTA). The CTA will appear in several places, sometimes rendered as a button or a card. The card may contain text with a link, or it may include a button. The CTA encourages the user to take some action.

For this project, we'll import the GitHub repository [bootstrap-small-business](https://github.com/rebeccapeltz/bootstrap-small-business) into replit.com. This repository is modified from the Start Bootstrap Small Business starter.  The starter only shows the index page.  Our modified repository contains additional pages for **about**, **contact**, and **service**.  The **nav** bar is set up in the index.html to access About and Contact.  Images have been added to the home page cards, and images are rendered that specify the image size needed.

### Code Patterns

It is helpful to look at code patterns and understand what they render when adding features to existing code.  A good way to start is to draw a schematic that blocks off sections of the web page and then map the code to those sections.  Look at the image above and then look at the code below that maps to it.  The goal is to be able to look at the code and visualize what it would look like rendered.  Look at the Notes on Bootstrap if you need to figure out what the effect of the Bootstrap CSS used.

#### Responsive Nav

The code below renders the nav bar on the home page.  As you look at this code, think about what would need to change for the about and contact pages.

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container px-5">
        <img class="icon-brand"  class="pe-3" src="./apple-brand.png" height="30px" width="auto" alt="brand">
        <a class="navbar-brand" href="./">(Site Name)</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
            data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
            aria-label="Toggle navigation"><span class="navbar-toggler-icon"></span></button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                <li class="nav-item"><a class="nav-link active" aria-current="page" href="#!">Home</a></li>
                <li class="nav-item"><a class="nav-link" href="./about.html">About</a></li>
                <li class="nav-item"><a class="nav-link" href="./contact.html">Contact</a></li>
            </ul>
        </div>
    </div>
</nav>
```

#### Column Row Cards

Most developers would agree that one of the challenges of reading and writing HTML is that there is a closing tag for most elements.  In the code below, you won't see all of the code on the page.  The `...` is a signal that there is code between two tags.  What you want to take away from this is that to render a `row` of columns (`col`), as seen in the product list, you need to render a `container`, followed by a `row`, and then a `col` containing a `card`.  Each `card` contains a `card-img-top`, a `card-body`, and a `div` with a `header` and text.

```html
<div class="container px-4 px-lg-5">
...
 <!-- new row in container -->
 <div class="row gx-4 gx-lg-5">
     <!-- new column in row -->
    <div class="col-md-3 mb-5">
        <div class="card h-100">
            <!-- Product image-->
            <img class="card-img-top" src="https://fakeimg.pl/300x200" alt="...">
            <!-- Product details-->
            <div class="card-body p-4">
                <div class="text-center">
                    <!-- Product name-->
                    <h5 class="fw-bolder">Fancy Product 1</h5>
                    <!-- Product price-->
                    $40.00 - $80.00
                </div>
            </div>
            <!-- Product actions-->
            <div class="card-footer p-4 pt-0 border-top-0 bg-transparent">
                <div class="text-center"><a class="btn btn-outline-dark mt-auto" href="#">View options</a></div>
            </div>
        </div>
    </div>
    ...
```

Creating your schematics with just pen and paper can help you to recognize code patterns and understand how the page was structured and styled.

### New Feature Requirements

<figure><img src="../.gitbook/assets/home-page.png" alt=""><figcaption><p>Home Page for Small Business Modified Starter</p></figcaption></figure>

Here are the steps to fulfill the requirements for adding content and features:

1. Import the  [bootstrap-small-business](https://github.com/rebeccapeltz/bootstrap-small-business) repository into a replit.com account
2. Render the home page and look at the code used to create it
3. Choose a business that will add content.  Your content will include text and images.  See the notes on content to find content.  Think about calls to action: what actions do you want your user to take?  In the code, you'll see that you can pop up an alert to indicate that action was taken as a button click.
4. Notice that some of the information is in parentheses. For that missing information, add data relevant to your business.
5. Add images to the home page.  These images represent products that your business sells.
6. Add Nav bars to the **about** and **contact** pages.  The **services** page is optional, but if you want to add that to your website, add it to each nav bar item list.  The links and the active class must be adjusted for each web page.  For example, on the home page, each product has a button.  In an e-commerce website, this button would take the user to a page where they see more information about the product.  You could create a page for each project or add an on-click alert, as shown in the examples below.

```html
<button onclick="alert('Button clicked!')">Click Me</button>
<a class="btn btn-outline-dark mt-auto" href="#" onclick="alert('Product 1 selected')">View options</a>

```

7. For text content, you can write your own or explore some of the results you get from AI.  The Microsoft Edge and Chrome browsers often generate lengthy responses that can help fill out the text content.  You can also sign up for free accounts at  [ChatGP](https://chat.openai.com/) and [Gemini](https://gemini.google.com/app).
8. The project comes with a favicon and brand icon featuring an apple. The favicon can be seen in the browser tab. The brand image is in the upper left corner of the nav bar.  This image came from downloading an icon image from [Iconduck](https://iconduck.com/).  To download this image, click on the icon and view its details.  Then, inspect the icon's image and open it in another tab to download it. Then, upload it into your replit.com project. ![](../.gitbook/assets/image.png)
9. There are three CSS files in the project. The **styles.css** contains the Bootstrap-generated CSS. The **stickyfooter.css** creates a footer that is always located at the bottom of the page, even if the content doesn't extend to that. The **custom.css** is a place where you can add your own CSS. Sometimes, you need to override the Bootstrap CSS, and the customer.css file should contain those overrides.  Load the services.html in your browser to see how the sticky footer looks.
10. On the About page, there are links for email and phone.  Try these out.  The `hrefs` for these links specify `tel` and `mailto`.  These prefixes will trigger the browser to locate an app that can use phone numbers or email data. &#x20;
11. Fill in the Copyright information.  This should be your name or the name of your business.

###

###

###

###

###
