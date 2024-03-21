# Project: Dynamic Style Change

In this project, we'll let the user specify the background color, font color, and font family by collecting data from a form.

The HTML and CSS for this project have already been written.  To complete the project, you will write the code that handles the Update button click.

* Locate the code for this project in GitHub:

[https://github.com/rebeccapeltz/js-event-handling/blob/main/update-style/index.html](https://github.com/rebeccapeltz/js-event-handling/blob/main/update-style/index.html)

* Look at the rendered page in GithHub:&#x20;

[https://www.beckypeltz.me/js-event-handling/update-style](https://www.beckypeltz.me/js-event-handling/update-style/)

* Create a Replit project and import the GitHub project [https://www.beckypeltz.me/js-event-handling](https://www.beckypeltz.me/js-event-handling/update-style/) into the Replit project.
* Add a JavaScript event handler to the update-style script.js file. The event handler is triggered by clicking on the Update Button.
* Use query selectors to get the data entered by the User.
* If the User didn't choose a Select element, the result will be an empty string `""`. Test for the empty string, and if it is false, set the style requested by the user. &#x20;
* Process the Radio button elements using querySelectorAll and the forEach method to find the checked button and then apply the user's font family style choice.  If none of the buttons are checked, don't make any changes.
* (optional) If the user doesn't select any changes on the form, you can use the `alert` function to let them know that nothing will be changed.

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>
