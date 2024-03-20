# Notes: HTML Forms

HTML Forms use elements to collect data. Once the data has been collected, JavaScript can process it in the browser.  Data processed in this way can be used to modify the DOM.  Forms can also submit data to servers.  In this course, we'll focus on processing the data in the browser and updating the DOM.

### Form Elements

The input tag is used to render form elements. Its type property determines the element's presentation on the web page and the type of data it holds.

As shown in the [Form Sampler,](https://replit.com/@RebeccaPeltz/form-sampler) many types are available for the input element.

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption><p>Input Sampler showing many available types</p></figcaption></figure>

We'll focus on the input types of `radio` and `text`.

#### Retrieve Data from an Input Element

To access data in an input element from JavaScript, use the `value` attribute.  The value attribute can also be set in JavaScript.  In the Input Sampler shown above, you can see data in the  `Number` and `Password` fields.  This is not `value` data but `placeholder` data.  The placeholder attribute provides a way to add instructions to the user from within an input element.

The sample code below shows how to access the input data's `value` and `type` using JavaScript.

```javascript
 document.querySelectorAll("input").forEach(function(inputData){
        let inputValue = inputData.value;
        let inputType = inputData.type;
        console.log(inputType, inputValue);
    });
```

#### Retrieve Data from Radio Buttons

Radio input buttons are rendered as tiny circles that are clickable.  In most cases, a set of radio buttons is expected to return a single value.  Each radio button is rendered as a separate input.  To create a set of related radio buttons, we add the name attribute, and all the radio buttons in a set get the same name.

The code below renders a set of radio buttons that allow the user to choose a `size` from Small, Medium, or Large.  We use the Label element to assign the selection values. &#x20;

```html
<div>
    <input type="radio" id="small" name="size" value="small" />
    <label for="small">Small</label>
</div>
<div>
    <input type="radio" id="medium" name="size" value="medium" />
    <label for="medium">Medium</label>
</div>
<div>
    <input type="radio" id="large" name="size" value="large" />
    <label for="large">Large</label>
</div>
```



<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption><p>Rendering a set of radio buttons</p></figcaption></figure>

To get the value of `size` we look for which item is checked.

```javascript
let selectedSize = "";
  document.querySelectorAll("[name='size']").forEach(function (size) {
    if (size.checked) {
      selectedSize = size.value;
      alert(selectedSize);
    }
  });
```

### Select Element



### Label Element



### Field Set

###



### Processing Form Inputs in Form Event Handler



### Updating the DOM Based on Form Content



### Resources

[W3 Select Element](https://www.w3schools.com/tags/tag\_select.asp)

[W3 Input Element](https://www.w3schools.com/tags/tag\_input.asp)

