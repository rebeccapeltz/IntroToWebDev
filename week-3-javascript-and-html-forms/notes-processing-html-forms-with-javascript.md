# Notes: Processing HTML Forms with JavaScript

HTML Forms use elements to collect data. Once the data has been collected, JavaScript can process it in the browser.  Data processed in this way can be used to modify the DOM.  Forms can also submit data to servers.  In this course, we'll focus on processing the data in the browser and updating the DOM.

### Form Elements

The input tag is used to render form elements. Its type property determines the element's presentation on the web page and the type of data it holds.

As shown in the [Form Sampler,](https://replit.com/@RebeccaPeltz/form-sampler) many types are available for the input element.

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption><p>Input Sampler showing many available types</p></figcaption></figure>

We'll focus on the input types of `radio` and `text`.

#### Retrieve Data from an Input Element

To access data in an input element from JavaScript, use the `value` attribute.  The value attribute can also be set in JavaScript.  In the Input Sampler shown above, you can see data in the  `Number` and `Password` fields.  This is not `value` data but `placeholder` data.  The placeholder attribute provides a way to add instructions to the user from within an input element.

The sample code below shows how to access the input data `value` and `type` using JavaScript.

```javascript
 document.querySelectorAll("input").forEach(function(inputData){
        let inputValue = inputData.value;
        let inputType = inputData.type;
        console.log(inputType, inputValue);
    });
```

#### Retrieve Data from Radio Buttons

Radio input buttons are rendered as tiny circles that are clickable.  A set of radio buttons is usually expected to return a single value.  Each radio button is rendered as a separate input.  To create a set of related radio buttons, we add the name attribute, and all the radio buttons in a set get the same name.

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
let radioSize = "";
  document.querySelectorAll("[name='size']").forEach(function (size) {
    if (size.checked) {
        radioSize = size.value;
      alert("radio:" + radioSize);
    }
});
```

### Select Element

The Select element presents a drop-down list of options for the user.  The code below will render a `select` element that allows the user to choose a size.

```html
<div>Select a Size:</div><br>
<select id="sizeSelector">
    <option value="small">Small</option>
    <option value="medium">Medium</option>
    <option value="large">Large</option>
</select><br><br>
```



<figure><img src="../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

#### Retrieve Data From Select Element

The code below demonstrates retrieving the data from a select element.

```javascript
let selectedSizeElement = document.querySelector("#sizeSelector");
selectedSize = selectedSizeElement.options[selectedSizeElement.selectedIndex].text;
alert("select:" + selectedSize);
```

### Label Element

The `label` tag renders a label element that provides a caption for an input.  The label is not used to store or extract data from the form.  It helps identify form elements to the user.  It aids accessibility as screen readers can use it to provide meaning to the input.

In the example below, the ID of the input is `bgcolor`.  The label is linked to an input using its for attribute whose value is the input's id.  In the examples above, inputs were identified by span and div, but this does not provide meaning.  The label is an inline element.  You can style it with CSS.

```html
<label for="bgcolor">Background Color:</label><br>
<input type="text" id="bgcolor" value="black"><br>
```

### Field Set and Legend

The `fieldset` is used to group related items in a form.  Like the label, It aids in accessibility. The fieldset can contain any input element at any time.  In the example below, it is used to indicate radio button nut preference.

```html
 <fieldset style="display:inline-block;width:30%;">
  <legend>Nut Preference</legend>
   <div>
     <input type="radio" id="almond" name="nut" value="almond" />
     <label for="almond">Almond</label>
   </div>

   <div>
     <input type="radio" id="walnut" name="nut" value="walnut" />
     <label for="walnut">Walnut</label>
   </div>
   <div>
     <input type="radio" id="peanut" name="nut" value="peanut" />
     <label for="peanut">Peanut</label>
   </div>
 </fieldset>
```

The code renders a list of radio buttons within a rectangle.&#x20;

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>Fieldset with Legend containing radio buttons</p></figcaption></figure>

### Processing Form Inputs in Form Event Handler

Processing the form data begins when the user clicks a button or other clickable element.  In the examples we've been working with, the clickable element is an `input` with type `button`.

```html
 <input id="update" type="button" value="Update">
```

The click event handlers are triggered when the user clicks on the Update button, which has an ID of `update`.  Instructions to select inputs and extract data are executed inside the handler function.  Like the window **"load"** event, the mouse "click" event is the function's first parameter.

```javascript
document.querySelector("#update").addEventListener("click", event => {
    document.querySelectorAll("input").forEach(function (inputData) {
      let inputValue = inputData.value;
      let inputType = inputData.type;
      console.log(inputType, inputValue);
    });

    let radioSize = "";
    document.querySelectorAll("[name='size']").forEach(function (size) {
      if (size.checked) {
          radioSize = size.value;
        alert("radio:" + radioSize);
      }
    });

    let selectedSizeElement = document.querySelector("#sizeSelector");
      selectedSize = selectedSizeElement.options[selectedSizeElement.selectedIndex].text;
   alert("select:" + selectedSize);
})
```

### Updating the DOM Based on Form Content

We've looked at updating the DOM after the Windows `load` event is triggered.  We can update the DOM after data has been entered in a form and a `click` event is triggered.

In this example, we allow the user to choose the font they want to see on their viewing page.

```html
<body>
  <h1>Manage Font Family</h1>
  <form>
    <fieldset>
      <legend>Select a font family:</legend>
      <div>
        <input type="radio" id="arialfont" name="fontFamily" value="Arial, sans-serif" checked />
        <label for="arialfont">Arial, sans-serif</label>
      </div>
      <div>
        <input type="radio" id="gilsans" name="fontFamily" value="Gill Sans, sans-serif" />
        <label for="gilsans">Gill Sans, sans-serif</label>
      </div>
      <div>
        <input type="radio" id="times" name="fontFamily" value="Times, Times New Roman, serif" />
        <label for="times">Times, Times New Roman, serif</label>
      </div>
    </fieldset>
    <br>
    <input id="update" type="button" value="Update"><br>
  </form>
  <script>
  document.querySelector("#update").addEventListener("click", event => {
    document.querySelectorAll("[name='fontFamily']").forEach(function (fontFamily) {
      if (fontFamily.checked) {
        document.body.style.fontFamily = fontFamily.value;
      }
    });
  });
  </script
```

We can start with a default browser font family and then use the chosen one after the update.

On the left, we see the default font family; on the right, after clicking on the update button, we see the Gil Sans font family.

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>Changing the Font Family base on Form InputInstructions to select inputs and extract data are executed inside the handler function</p></figcaption></figure>

### Resources

[W3 Select Element](https://www.w3schools.com/tags/tag\_select.asp)

[W3 Input Element](https://www.w3schools.com/tags/tag\_input.asp)

[W3 Fieldset Element](https://www.w3schools.com/tags/tag\_fieldset.asp)

[MDN Introduction to Events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building\_blocks/Events)



