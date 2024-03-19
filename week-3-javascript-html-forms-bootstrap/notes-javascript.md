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

### Variables

Variables are found in most programming languages.  They are references to data.  Variables are created by declaring their name and value.  Variable declaration begins with a keyword that describes the variables accessbility on the page that is was declared on.



* `var` creates a variable that is function scoped, but if is declared outside of a function it becomes global scoped. The `var` declaration is not used much any more as it can lead to unexpected results. In general, global scoping isn't a good way to declare variable.  It's better to keep variable declaration close to the data they are holding.
* `let` creates a variable that is block scoped. A block in JavaScript means the code that is contained within 2 curly braces {...}.  Values declare with `let` can be changed in the block.
* `const` which is short for constant creates a variable that is block scoped.  It differs from `let` in that a `const` variable cannot be reassigned a value.

The code below shows how to declare variables in JavaScript.  The `console.log` command will log information to the browser console.  Browser consoles are accessed by opening the Inspector.  The Chrome browser is accessed by clicking on **View | Developer | Inspect.**&#x20;

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

```javascript
// var declaration
var age = 21;
var newAge = age + 1;
age = 25;
console.log(age)
```

If we paste the code above into the JavaScript consold and hit return, the code will be executed and the value 25 will be returned.

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>Executing JavaScript in the Chrome Browser Console</p></figcaption></figure>

### Selecting Elements in JavaScript

JavaScript provides the document.queryselector function to enable programmatic selection of DOM elements.  Similar to CSS, JavaScript can select by element type, class, or ID.  Once an element is selected, it can be modified. Modifying an element can mean changing it's CSS or attributes. &#x20;

If you select by ID there will be only one element found if the ID exists on the page, but if you select by class or type, there will be 0 or more elements found because there can be multiple elements with of the same type of using the same CSS class.

```
// Some cod
```







### Variables and Operators





### Functions



### Event Handling

###



### Modifying Style in JavaScript



### Resources

[W3 Script Tag Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

