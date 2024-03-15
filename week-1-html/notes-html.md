# Notes: HTML

HTML is an acronym for **Hypertext Markup Language**. It is a declarative language, meaning it instructs by providing code that tells the browser how to organize and render content. Content may be text, images, video, audio and other types of media.

### Browsers

HTML is interpreted by browsers.  Not all browser are the same.  The chart below from [Statista](https://www.statista.com/statistics/268254/market-share-of-internet-browsers-worldwide-since-2009/) shows that Google Chrome has the most market share, followed by Apple Safari and Microsoft Edge. &#x20;

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p>Browser Market Share since 2012</p></figcaption></figure>

The HTML language is always evolving.  If you want to find out if the HTML you are using will work in the browsers that you are supporting, you can visit the [caniuse](https://caniuse.com/) page. In the picture below, caniuse is reporting that the HTML table tag element is supported in all of the browsers.

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

### Containment

The word containment refers to the way in which HTML element may or may not contain other HTML elements or text.  Many elements will contain other elements or text. &#x20;

The examples below show elements that contain text.

`<h1>Title at the Top of the Page</h1>`

`<p>This is a paragraph.</p>`

The example below shows and element, ordered list that contain other elements which are list items.

`<ol>`

&#x20;   `<li>Item 1</li>`

&#x20;   `<li>Item2</li>`

`</ol>`

In the code below, figure contains an image and a figure caption.  The image element, `img`, will not contain any other elements.  The figure caption, `figcaption`, element contains text.

`<figure>`

&#x20;   `<img src="dog.jpg">`

&#x20;   `<figcaption>This is my dog</figcaption>`

`</figure>`

In the table at the bottom of this page, elements that don't use closing tags will not contain other elements.  These elemen are marked "no" for closing.

### Block and Inline HTML Elements

The concepts of Block and Inline HTML are important in setting up page layout.  As CSS is added to a page, knowing which elements are block and which are inline will become more important.

For now, it's helpful to understand that block elements use the entire width of the page and therefore any elements following them will be rendered on the next line.  Inline elements will be rendered on the same line.

Images are inline elements.  If we want images to be rendered on a line by themselves we need to contain them in a block element.  Here is an example of containing them in a `div` element.

`<div>`

&#x20;   `<img src="dog.jpg">`

`</div>`

`Just because an HTML tag element has a closing tag doesn't make it a block element.  For example a span tag contains text that will be rendered on the same line.`

`<span>This is important text.</span>`

### Semantic HTML

Just like spoken languages evolve so has HTML.  Years ago div and span were used as containers for most web pages.  Semantic HTML tag elements were introduced to so that the structure that HTML provides would also have meaning.  This is important for accessibility.  While it is possible to style a div element to look like a button element, the meaning is not the same.  The word "semantic" is defined as "meaning in a language".&#x20;

Screen readers that read web pages for visually impaired users can take advantage of semantic HTML.  For example, if a developer uses an article element instead of a div element, it can inform the user that it is reading an article.  Visually, the browser would render the article and element the same, so in that respect these tags are interchangeable.  If the developers is thinking about accessibility, then these tags are very different.

### HTML Attributes

The HTML langage is made up of tags that render elements in the browser.  HTML attributes are bits of language markup that supplement the behavior and/or look of the rendered element.  Attributes are words followed by an equal sign and quoted text or numbers. &#x20;

In the example below the images have source, `src`, `height` and `width` attributes.  The source attribute tells the browser where to get the image and the height and width tell it how to size it on the web page. In this example `dog.jpg` refers to an image files with the name `dog.jpg` that is in the same directory as the HTML file.  The width attribute is set to `400px`.  A `px` is a unit of measure that is shorthand for pixel.  You can think of a pixel as a unit of light that is emitted on computer screen.  This means that the width of the image will be rendered as 400 of these units wide.  To put this in perspective, a mobile device averages 350 pixels and a laptop averages about 1920 pixels.  The height attribute is set to "auto".  This ensures that the image won't look funny due to stretching and removing the aspect ratio.&#x20;

`<img src="dog.jpg" width="400px" height="auto">`

Here's another example where attributes are used.  In this example, an anchor tag is used to render a clickable link.  The href attribute is set to a URL that the user can go to jus by clicking on the link.  The href attribute name is shorthand for hypertext reference.  The term "web" used to describe the internet, came about because of the way sites all over the world are connected by these links.

`<a href="https://www.example.com">Example Link</a>`

### Categorized List of HTML Element Tags

<table><thead><tr><th width="136">Category</th><th width="156">Tags</th><th width="92">Closing</th><th>Tag Example</th></tr></thead><tbody><tr><td>Document</td><td></td><td></td><td></td></tr><tr><td></td><td>!DOCTYPE html</td><td>no</td><td>&#x3C;!DOCTYPE html></td></tr><tr><td></td><td>&#x3C;! Comments --></td><td>no</td><td><code>&#x3C;!-- Comments --></code></td></tr><tr><td></td><td>html</td><td></td><td><code>&#x3C;html>...&#x3C;/html></code></td></tr><tr><td>Meta Data</td><td></td><td></td><td></td></tr><tr><td></td><td>base</td><td>no</td><td>default target for links  <code>&#x3C;base href="https://www.example.com" target="_blank" ></code></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td>head</td><td></td><td>&#x3C;head>...&#x3C;/head></td></tr><tr><td></td><td>link</td><td>no</td><td>link to CSS file<code>&#x3C;link href="style.css" rel="stylesheet" type="text/css" /></code></td></tr><tr><td></td><td>meta</td><td>no</td><td><code>&#x3C;meta name="viewport" content="width=device-width"></code></td></tr><tr><td></td><td>style</td><td></td><td>local CSS <code>&#x3C;style>...&#x3C;/style></code></td></tr><tr><td></td><td>title</td><td></td><td>title appears in the tab of the browser <code>&#x3C;title>...&#x3C;/title></code></td></tr><tr><td>Structure</td><td></td><td></td><td></td></tr><tr><td></td><td>address</td><td></td><td><code>Contact Information &#x3C;address>...&#x3C;/address></code></td></tr><tr><td></td><td>article</td><td></td><td><code>&#x3C;article>...&#x3C;/article></code></td></tr><tr><td></td><td>aside</td><td></td><td><code>&#x3C;aside>...&#x3C;/aside></code></td></tr><tr><td></td><td>body</td><td></td><td><code>&#x3C;body>...&#x3C;/body></code></td></tr><tr><td></td><td>div</td><td></td><td><code>&#x3C;div>...&#x3C;/div></code></td></tr><tr><td></td><td>footer</td><td></td><td><code>&#x3C;footer>...&#x3C;/footer></code></td></tr><tr><td></td><td>h1</td><td></td><td><code>&#x3C;h1>...&#x3C;/h1></code></td></tr><tr><td></td><td>h2</td><td></td><td><code>&#x3C;h2>...&#x3C;/h2></code></td></tr><tr><td></td><td>h3</td><td></td><td><code>&#x3C;h3>...&#x3C;/h3></code></td></tr><tr><td></td><td>h4</td><td></td><td><code>&#x3C;h4>...&#x3C;/h4></code></td></tr><tr><td></td><td>h5</td><td></td><td><code>&#x3C;h5>...&#x3C;/h5></code></td></tr><tr><td></td><td>h6</td><td></td><td><code>&#x3C;h6>...&#x3C;/h6></code></td></tr><tr><td></td><td>header</td><td></td><td><code>&#x3C;header>...&#x3C;/header></code></td></tr><tr><td></td><td>paragraph</td><td></td><td><code>&#x3C;p>...&#x3C;/p></code></td></tr><tr><td></td><td>nav</td><td></td><td><code>&#x3C;nav>...&#x3C;/nav></code></td></tr><tr><td></td><td>section</td><td></td><td><code>&#x3C;section>...&#x3C;/section></code></td></tr><tr><td></td><td>span</td><td></td><td><code>&#x3C;span>...&#x3C;/span></code></td></tr><tr><td>Grouping</td><td></td><td></td><td></td></tr><tr><td></td><td>blockquote</td><td></td><td><code>&#x3C;blockquote citation="URL">...&#x3C;/blockquote></code></td></tr><tr><td></td><td>dd</td><td></td><td>definition contained in description list <code>&#x3C;dd>...&#x3C;/dd></code></td></tr><tr><td></td><td>dl</td><td></td><td>description list <code>&#x3C;dl>...&#x3C;/dd></code></td></tr><tr><td></td><td>dt</td><td></td><td>term contained in description list <code>&#x3C;dt>...&#x3C;/dt></code></td></tr><tr><td></td><td>figure</td><td></td><td>contain photos, diagrams, code, figcaption <code>&#x3C;figure>...&#x3C;/figure></code></td></tr><tr><td></td><td>figcaption</td><td></td><td><code>&#x3C;figcaption>...&#x3C;/figcaption></code></td></tr><tr><td></td><td>hr</td><td>no</td><td>horizonal rule <code>&#x3C;hr></code></td></tr><tr><td></td><td>li</td><td></td><td>list item  contained in ordered or unordered list<code>&#x3C;li>...&#x3C;/li></code></td></tr><tr><td></td><td>ol</td><td></td><td>ordered list <code>&#x3C;ol>...&#x3C;/ol></code></td></tr><tr><td></td><td>pre</td><td></td><td>preformatted text <code>&#x3C;pre>...&#x3C;/pre></code></td></tr><tr><td></td><td>ul</td><td></td><td>unordered list <code>&#x3C;ul>...&#x3C;/ul></code></td></tr><tr><td>Embedding</td><td></td><td></td><td></td></tr><tr><td></td><td>area</td><td>no</td><td>defines coordinates inside image map <code>&#x3C;area ></code></td></tr><tr><td></td><td>audio</td><td></td><td>contains source for audio files <code>&#x3C;audio>...&#x3C;/audio></code></td></tr><tr><td></td><td>canvas</td><td></td><td>area on web page for drawing graphics <code>&#x3C;canvas>...&#x3C;/canvas></code></td></tr><tr><td></td><td>embed</td><td>no</td><td>container for external source like video <code>&#x3C;embed></code></td></tr><tr><td></td><td>iframe</td><td></td><td>container to embed a web page from another server <code>&#x3C;iframe src="" title="">...&#x3C;/iframe></code></td></tr><tr><td></td><td>img</td><td>no</td><td>image <code>&#x3C;img srce="" height="" width=""></code></td></tr><tr><td></td><td>map</td><td></td><td>make clickable areas in different parts of a single image <code>&#x3C;map>...&#x3C;/map></code></td></tr><tr><td></td><td>object</td><td></td><td>embed external source like video player, web page <code>&#x3C;object>...&#x3C;/object></code></td></tr><tr><td></td><td>param</td><td>no</td><td>define parameters in an object <code>&#x3C;param>...&#x3C;/param></code></td></tr><tr><td></td><td>picture</td><td></td><td>contain images for responsive web pages <code>&#x3C;picture>...&#x3C;/picture></code></td></tr><tr><td></td><td>source</td><td>no</td><td>media sources for video, audio and pictures <code>&#x3C;source  src="" type=""></code></td></tr><tr><td></td><td>track</td><td>no</td><td>used for subtitles and caption in video and audio <code>&#x3C;track src="" kind="" srclang="" label=""></code></td></tr><tr><td></td><td>video</td><td></td><td><code>&#x3C;video>...&#x3C;/video></code></td></tr><tr><td>Forms</td><td></td><td></td><td></td></tr><tr><td></td><td>button</td><td></td><td><code>&#x3C;button>...&#x3C;/buton></code></td></tr><tr><td></td><td>datalist</td><td></td><td>list of selectable options <code>&#x3C;datalist>...&#x3C;/datalist></code></td></tr><tr><td></td><td>fieldset</td><td></td><td>group related form elements <code>&#x3C;fieldset>...&#x3C;/fieldset></code></td></tr><tr><td></td><td>form</td><td></td><td><code>&#x3C;form>...&#x3C;/form></code></td></tr><tr><td></td><td>input</td><td>no</td><td><code>&#x3C;input type="" value="" id="" name="" ></code></td></tr><tr><td></td><td>label</td><td></td><td><code>&#x3C;label for="">&#x3C;/label></code></td></tr><tr><td></td><td>legend</td><td></td><td>caption for a fieldset <code>&#x3C;legend>...&#x3C;/legend></code></td></tr><tr><td></td><td>meter</td><td></td><td>renders a bar showing a measurement <code>&#x3C;meter value="" min="" max="">...&#x3C;/meter></code></td></tr><tr><td></td><td>optgroup</td><td></td><td>group related options in a select <code>&#x3C;optgroup label="">...&#x3C;/optgroup></code></td></tr><tr><td></td><td>option</td><td></td><td>option contained by optgroup, select or datalist <code>&#x3C;option value="">...&#x3C;/option></code></td></tr><tr><td></td><td>output</td><td></td><td>output of a calculation <code>&#x3C;output>...&#x3C;/output></code></td></tr><tr><td></td><td>progress</td><td></td><td>progress bar <code>&#x3C;progress value="" max="">&#x3C;/progress></code></td></tr><tr><td></td><td>select</td><td></td><td>select from a list of options <code>&#x3C;select>...&#x3C;/select></code></td></tr><tr><td></td><td>textarea</td><td></td><td>multiline text input <code>&#x3C;textarea rows="" cols="">...&#x3C;/textarea></code></td></tr><tr><td>Tabular</td><td></td><td></td><td></td></tr><tr><td></td><td>caption</td><td></td><td>table caption <code>&#x3C;caption>...&#x3C;/caption></code></td></tr><tr><td></td><td>col</td><td>no</td><td>properties for a colgroup <code>&#x3C;col span="" style=""></code></td></tr><tr><td></td><td>colgroup</td><td></td><td>contains a set of cols <code>&#x3C;colgroup>...&#x3C;/colgroup></code></td></tr><tr><td></td><td>table</td><td></td><td><code>&#x3C;table>...&#x3C;/table></code></td></tr><tr><td></td><td>tbody</td><td></td><td>body of the table <code>&#x3C;tbody>...&#x3C;/tbody></code></td></tr><tr><td></td><td>td</td><td></td><td>table detail is a cell in the table <code>&#x3C;td>...&#x3C;/td></code></td></tr><tr><td></td><td>tfoot</td><td></td><td>table footer <code>&#x3C;tfoot>...&#x3C;/tfoot></code></td></tr><tr><td></td><td>th</td><td></td><td>table header cell <code>&#x3C;th>...&#x3C;/th></code></td></tr><tr><td></td><td>thead</td><td></td><td>table header <code>&#x3C;thead>...&#x3C;/thead></code></td></tr><tr><td></td><td>tr</td><td></td><td>table is made of of rows containing cells table row <code>&#x3C;tr>...&#x3C;/tr></code></td></tr><tr><td>Interactive</td><td></td><td></td><td></td></tr><tr><td></td><td>details</td><td></td><td>container for interactive content that can be opened and closed by user <code>&#x3C;details>...&#x3C;/details></code></td></tr><tr><td></td><td>summary</td><td></td><td>heading you see for details &#x3C;summary>...&#x3C;/summary></td></tr><tr><td></td><td>dialog</td><td></td><td>container where you show content by adding an "open" attribute <code>&#x3C;dialog>...&#x3C;/dialog></code></td></tr><tr><td>Script</td><td></td><td></td><td></td></tr><tr><td></td><td>noscript</td><td></td><td>alternate content if you brower doesn't support javascript <code>&#x3C;noscript>...&#x3C;/noscript></code></td></tr><tr><td></td><td>script</td><td></td><td>JavaScript rendered on the web page <code>&#x3C;script src="script.js">...&#x3C;/script></code></td></tr><tr><td></td><td>template</td><td></td><td>hidden content container that can be rendered later using JavaScript <code>&#x3C;template>...&#x3C;/template></code></td></tr></tbody></table>

Resources

[W3 Schools HTML](https://www.w3schools.com/html/)

[W3 Schools Block and Inline Elements\
](https://www.w3schools.com/html/html\_blocks.asp)
