# Notes: JavaScript

###

JavaScript is one of the most popular programming languages in the world. Along with HTML and CSS, it is considered a core technology for the web. JavaScript is an imperative language, meaning that instructions are provided as sequential commands, unlike HTML and CSS. JavaScript commands usually result in "state" changes. The term "state" in programming refers to a variable or system's value at a given time.

JavaScript is used in both browsers and servers. Humans interact with browsers, and servers interact with browsers and other servers. The term "Front-end" developer refers to a developer who writes applications that run on browsers and mobile devices. "Back-end" developer refers to developers who write application programming interfaces (APIs).

Back-end developers use Node.js to write APIs and create servers. Node.js executes JavaScript outside of the browser.  It can run JavaScript code on a server or from the command line.

JavaScript in the browser makes it possible to create interactive applications where users can change state and modify data.

### Loading JavaScript Code in the Browser

The `<script>` tag is used to load JavaScript in the browser.  JavaScript can also be loaded from an external file using the `<link>` tag or specified as text within a `<script>` tag.

#### Loading JavaScript from a Local File&#x20;

Use a script tag to load a local file.

```html
<!-- load from a local file -->
<script src="myscript.js"></script>
```

#### Loading JavaScript as Text  In a Script Tag

Use a script tag to add JavaScript text to an HTML file.

<pre class="language-html"><code class="lang-html">&#x3C;!-- load using JavaScript text -->
&#x3C;script>
<strong>    document.querySelector("h1").innerHTML = "Hello World";
</strong>&#x3C;/script>    
</code></pre>

#### Loading JavaScript from an External File on the Web

Use a `link` tag and specify the URL to the JavaScript file in an `href` attribute.

```html
<!-- load from a file on the web -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
```

### Events

JavaScript is and event driven language.  This means that functionality is executed when events are triggered.  The table below shows categories of events and what triggers them.



<table><thead><tr><th width="230">Event Category</th><th>Triggers</th></tr></thead><tbody><tr><td>Keyboard</td><td><code>keydown</code>, <code>keyup</code>, and <code>keypress</code></td></tr><tr><td>Mouse</td><td><code>click</code>, <code>mousedown</code>, <code>mousemove</code>, and <code>mouseup</code></td></tr><tr><td>Form</td><td><code>submit</code>, <code>change</code>, and <code>input</code></td></tr><tr><td>Window</td><td><code>load</code>, <code>resize</code> and <code>scroll</code>.</td></tr><tr><td>CSS</td><td><code>transitionend</code> and <code>animationend</code></td></tr></tbody></table>

Events enable user interaction that changes data and the DOM.  In addition to reading, writing, updating, and deleting data, JavaScript can create, update and delete HTML Elements.  It can also apply CSS to elements that it selects. &#x20;

### Variables and Operators

Variables are found in most programming languages.  They are references to data.  Variables are created by declaring their name and value.  The variable declaration begins with a keyword that describes the variable's accessibility on the page that it was declared on.



* `var` It creates a function-scoped variable, but it becomes global-scoped if declared outside of a function. The `var` declaration is no longer used as it can lead to unexpected results. In general, global scoping isn't an excellent way to declare variables.  It's better to keep variable declarations close to their holding data.
* `let` Creates a variable that is block-scoped. A block in JavaScript means the code contained within two curly braces {...}.  Values declare with `let` can be changed in the block.
* `const` Which is short for constant and creates a variable that is block-scoped.  It differs from `let` in that a `const` variable cannot be reassigned as a value.

The code below shows how to declare variables in JavaScript.  The `console.log` command will log information to the browser console.  Browser consoles are accessed by opening the Inspector.  The Chrome browser is accessed by clicking on **View | Developer | Inspect.**&#x20;

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>View JavaScript Console in Chrome</p></figcaption></figure>

We'll start with `var`, and then use let and const.  Both `var` and `let` examples will return the same value, but the code for `const` will fail because it does not allow reassignment.

```javascript
// var declaration
var age = 21;
var newAge = age + 1;
age = 25;
console.log(age)
```

If we paste the code above into the JavaScript console and hit return, the code will be executed, and the value 25 will be returned.

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption><p>Executing JavaScript in the Chrome Browser Console using var declaration</p></figcaption></figure>

```
// let declaration
let age = 21;
let newAge = age + 1;
age = 25;
console.log(age)
```

<figure><img src="../.gitbook/assets/image (46).png" alt=""><figcaption><p>Executing JavaScript in Chrome console using let declaration</p></figcaption></figure>

```
// const declaration
const age = 21;
const newAge = age + 1;
age = 25;
console.log(age)
```

<figure><img src="../.gitbook/assets/image (47).png" alt=""><figcaption><p>Executing JavaScript in Chrome console using const desclaration results in error</p></figcaption></figure>

The `+` (plus sign) used in the code above is an operator.  Operators provide a way to change data.  The `=` (equals) is a way to capture the changed data in memory by modifying the system's state.



### Selecting Elements in JavaScript

JavaScript provides the document.queryselector function to enable programmatic selection of DOM elements.  Similar to CSS, JavaScript can select by element type, class, or ID.  Once an element is selected, it can be modified. Modifying an element can mean changing it's CSS or attributes. &#x20;

There are two commands used to select elements on a page: `querySelector` and `querySelectorAll`.   If we select element types, like all the paragraphs on a page, or classes, like all the elements with a class name "container",  we would use `querySelectorAll`.  If we only want the first element of a set of types or classes, or we are selected by ID, then we use `querySelector`.

We can group elements by type, class, and ID from the HTML shown below.  The number of elements for each category is shown in parentheses.

* header1 (1)
* paragraph (4)
* ID is "unique" (1)
* class is "big" (2)

```html
<body>
  <h1>Hello world</h1>
  <p>This is a paragraph.</p>
  <p>This is another paragraph.</p>
  <p id="unique">This is a <span class="big">unique</span> paragraph.</p>
  <p class="big">This is a big paragraph.</p>
</body>
```

The `querySelector` returns an element, but the `querySelectorAll` returns a list of elements.  We can only apply changes to one element at a time.  Therefore, when we use `querySelectorAll` we have to loop through the list of element returns and make changes one at a time.

Both `querySelector` and `querySelectorAll` are functions that are related to the DOM.  They are part of the `document` object.  We'll soon see how they are used to modify the DOM.



<table><thead><tr><th width="282">Selection Criteria</th><th width="297">Function Call</th><th width="245">Returned</th></tr></thead><tbody><tr><td>select all paragraphs</td><td>document.querySelectorAll("p")</td><td>list of 4 elements</td></tr><tr><td>select header1</td><td>document.querySelector("h1")</td><td>1 element</td></tr><tr><td>select all elements with the "big" class specified</td><td>document.querySelectorAll(".big")</td><td>list of 2 elements</td></tr><tr><td>select element with ID equal to "unique"</td><td>document.querySelector("#unique")</td><td>1 element</td></tr><tr><td>select just the first paragraph found in the page</td><td>document.querySelector("p")</td><td>1 element</td></tr></tbody></table>

Notice that when selecting a class, we preface the name with a period `.` . When we select based on an ID, we preface the ID with a hash `#` . This is similar to what we do in CSS.  When Returned is a list of elements, we need to loop through the list to apply changes one at a time.

We've seen that querySelector and querySelectorAll are functions of the document object. Let's see how to write JavaScript Functions.

###

### Functions

JavaScript functions are blocks of code that perform a task.  They can receive input parameters and return output values.   To work with functions, we need to understand data types. &#x20;

#### Data Types

JavaScript data types are listed below.

* String
* Number
* Bigint
* Boolean
* Undefined
* Null
* Symbol
* Object



<table><thead><tr><th width="337">Data Type</th><th>Example</th></tr></thead><tbody><tr><td>String*</td><td>"hello", "my dog's name is Fluff",  "I am 5 years old"</td></tr><tr><td>Number*</td><td>1, .5, 3.1415, 10000, -1</td></tr><tr><td>Bigint (needed for very large numbers) </td><td>1234567890123456789012345n</td></tr><tr><td>Boolean*</td><td>true, false</td></tr><tr><td>Undefined*</td><td>declared but not initialized</td></tr><tr><td>Null</td><td>null</td></tr><tr><td>Symbol</td><td>MY_CONSTANT</td></tr><tr><td>Object</td><td>{name: "Fluff", age: 7}</td></tr></tbody></table>

&#x20;\*We'll be focusing on the String, Number, Boolean and Undefined types

#### Using String and Number Types in a Function

This JavaScript function uses String and Number types to build a new string.  The function `introduce` has two **parameters**: `name` and `age`.  It uses String concatenation (adding strings and numbers  with the `+` operator to create a new string) to create and return the introduction String. The function name calls the function and passes in two values, which are referred to as **arguments**.  Think of the values passed to a function as arguments and the values received by the function as **parameters**.

In the central part of the script, we initialize the subject variable with a let declaration that references the value returned by the function.  For the second call, we don't use `let` in the declaration, because it has already been used in the first declaration, we reassign the reference to point to a new value returned by the `introduce` function based on new arguments for name and age.

The alert function is a built-in JavaScript function that pops up a small window containing the string passed to it.  Using the alert function is helpful in the same way that console.log is: it shows the state of a variable at a given point in the code.

```
 <script>
    function introduce(name, age) {
      const whoAmI = "My name is" + name + " and I am " + age + " years old." 
      return whoAmI;
    }
    let subject = introduce("Fluff",7);
    alert (subject);
    subject = introduce("Spot",3)
    alert (subject2);
    
  </script>
```

Executing the code in a Replit application, we see the alert looks like this:

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>Alert the value returned by the introduce function and stored in the subject variable</p></figcaption></figure>

The alert is a popup and the OK button will close it.



### Interpolation vs Concatenation

#### Concatenation

In the code in the previous section, we used concatenation to create a string from another string and a number. &#x20;

<pre class="language-javascript"><code class="lang-javascript"><strong>let smallInteger = 7;
</strong><strong>let smallString = "small: " + smallInteger;
</strong><strong>console.log(smallInteger);
</strong><strong>// expected logged value: "small: 7"
</strong></code></pre>

We use the plus operator (`+`) to concatenate a variable to a string.  We can use concatenation with string, number, and boolean variables, and the result will be a string.

#### Interpolation

Interpolation allows developers to insert variables into an existing string.  The existing string is created using the backtick character (`` ` ``) instead of the single (`')` or double (`"`) quote.  The backtick characters are located on the top of the keyboard, just to the left of the number 1.  To insert a variable values, we enclose the variable in dollar sign curly braces (`${...}`).

The code below shows how to insert a variable into the interpolation string to achieve the same result as the above concatenation code.&#x20;

```javascript
let smallInteger = 7;
let smallString = `small: ${smallInteger}`;

console.log(smallString);
// expected logged value: "small: 7"
```

Here's a sample that uses multiple variables in a larger string.  Notice that I can call functions inside the parameter slots. In this example, I am formatting numbers.  The interpolation string can accept different data types and functions that act on data.

<pre class="language-javascript"><code class="lang-javascript">let year = 2024;
let comp = 16438.77;
<strong>let compRise = 0.42;
</strong>let openingPrice = 16517.241;
<strong>const summary = `NASDAQ Composite Index (COMP) ${year}: The COMP index is 
</strong><strong>currently at ${comp.toLocaleString('en-US')} points, with a ${compRise.toFixed(2)}% rise. The intraday low matches 
</strong><strong>the current value, and the opening price was ${openingPrice.toLocaleString('en-US')}.`;
</strong><strong>
</strong><strong>console.log(summary);
</strong><strong>// expected logged value:
</strong><strong>// NASDAQ Composite Index (COMP): The COMP index is 
</strong>// currently at 16,438.77 points, with a 0.42% rise. The intraday low matches 
// the current value, and the opening price was 16,517.241.
</code></pre>

#### Which Method Should We Use?

The **interpolation** method is the newer method for creating strings with variable data, and it is the preferred method.  In the concatenation example, we had to add a space after `small:` . It is more natural to set up a template string for interpolation and then fill in variables than to try to add spacing and punctuation one variable at a time.

### Event Handling

The browser triggers events based on user interaction and web page loading.  Functions that respond to these events are called Event Handlers.   Let's look at code for an event handler that modifies page style and content based on the window loading, completing the page `load`.  Executing a function on load is an everyday use case.

When a page loads, the browser parses the HTML to figure out what needs to be done.  If there are link tags for CSS or script tags for JavaScript files, the browsers will request those, and the element tags will render the content.  We can listen for the load event to be completed and then execute JavaScript to modify the loaded page.

#### Apply Changes on the Window Load Event

We'll be loading the HTML specified in an earlier section.

```html
 <h1>Hello world</h1>
  <p>This is a paragraph.</p>
  <p>This is another paragraph.</p>
  <p id="unique">This is a <span class="big">unique</span> paragraph.</p>
  <p class="big">This is a big paragraph.</p>
```

We need to listen for the completion of the page load and then call a function to modify the page.  The listener is set up below.  The window object has an addEventListener function that takes two parameters: 1) an event string and 2) a function.  The function always receives an event parameter from the event itself.

```javascript
 window.addEventListener('load', function (event) {
      // execute code here
      })
    });
```

The code inside the listener function will not be executed until the function receives notification that the event has occurred.

The code below shows the listener wrapped around the instructions to be executed on load.

```javascript
  // Wait for the window to complete loading
  window.addEventListener('load', function () {
      // Change the content of h1 from "Hello World" to "Hello Universe"
      // Change content by setting innerHTML to a string value
      document.querySelector("h1").innerHTML = "Hello Universe";
      
      // Create a local variable that references the element with an ID of unique
      let uniqueEl = document.querySelector("#unique");
      // Change the background color of the unique element to yellow and its font
      // family to sans-serif
      // Change style by setting the style.<property> to a string value
      uniqueEl.style.backgroundColor = "yellow";
      uniqueEl.style.fontFamily = "sans-serif";
      
      // Select all paragraphs and use the forEach function provided by list objects 
      // to iterate through all the paragraphs and change their background color to 
      // light green
      document.querySelectorAll("p").forEach(function (p) {
        p.style.backgroundColor = "lightgreen";
      });
     
      // Select all elements that have the class "big" and use the forEach 
      // function provided by list objects to set their font family to 
      // "sans-serif and their font size to "50px"
      let bigEl = document.querySelectorAll(".big");
      bigEl.forEach(el=>{
        el.style.fontFamily = "sans-serif";
        el.style.fontSize = "50px";
      })
    });
```

In the code above, we can see how to deal with selectors that return multiple elements. When multiple elements are selected, the return type is a list object. We see that the list object provides a function `forEach`. The `forEach` function pulls out one list element at a time in sequence and passes it to a new function, where the single element can be modified.

Functions don't always have names like the `introduce` function we looked at.  Functions without names are called anonymous functions.  Functions also don't always return values.  In the `forEach` function, we instruct an anonymous function to be called with a parameter taken from the list.  Inside the anonymous function, we provide instructions that take effect immediately.  There is no need to return a value.

When a selector returns a single value, we can operate on it immediately without having to use `forEach.`

The code changes content and style.  JavaScript changes style by accessing the elements style property and assigning a string value.  In the code above, we change the style for `backgroundColor`, `fontFamily`, and `fontSize`.  The properties in CSS are changed to JavaScript properties by removing the `-` (dash) and setting the word following the dash to upper case.

* background-color -> backgroundColor
* font-family -> fontFamily
* font-size -> fontSize

Before running the window `load` function, the page looked like this:

<figure><img src="../.gitbook/assets/image (48).png" alt=""><figcaption><p>Web Page before calling window.load event handler</p></figcaption></figure>

After running the window `load` function, the page looks like this:

<figure><img src="../.gitbook/assets/image (49).png" alt=""><figcaption><p>After executing the window load event handler</p></figcaption></figure>

The header1 content has changed. Three of the four paragraphs have a green background, and the paragraph with the unique ID has a yellow background. Where elements were assigned the "big" class, the font size is now large and sans-serif.&#x20;

### Resources

[W3 Script Tag Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

[W3 Schools Arithmetic Operators](https://www.w3schools.com/js/js\_operators.asp)

[W3 Schools Style Properties in JavaScript](https://www.w3schools.com/jsref/dom\_obj\_style.asp)

[MDN Window Load Event](https://developer.mozilla.org/en-US/docs/Web/API/Window/load\_event)

