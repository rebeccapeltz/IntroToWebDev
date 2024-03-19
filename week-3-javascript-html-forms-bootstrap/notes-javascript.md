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

### DOM Events



### Selecting Elements in JavaScript



### Modifying Style in JavaScript



### Resource

[W3 Script Tag Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

