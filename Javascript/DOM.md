# Document Object Model

## Methods

### querySelector

The `querySelector` method in the Document Object Model (DOM) allows you to select the first element within the document that matches a specified selector, or group of selectors. It returns `null` if no matches are found.

For example, if you have an HTML element with the class "example", you could select it with `document.querySelector('.example')`.

### getElementById

The `getElementById` method allows you to select an element by its unique ID. It returns a reference to the first object with the specified ID, or `null` if the ID is not found.

For example, if you have an HTML element with the ID "example", you could select it with `document.getElementById('example')`.

### getElementsByTagName

The `getElementsByTagName` method allows you to select all elements within the document with a specified tag name. It returns a live `HTMLCollection` of elements with the given tag name. The elements in the returned collection are sorted as they appear in the source code.

For example, if you want to select all `<p>` elements in the document, you could do so with `document.getElementsByTagName('p')`.

### querySelectorAll

The `querySelectorAll` method allows you to select all elements within the document that match a specified selector, or group of selectors. Unlike `querySelector`, which only returns the first match, `querySelectorAll` returns a `static NodeList` representing a list of the document's elements that match the specified group of selectors.

For example, if you have multiple HTML elements with the class "example", you could select all of them with `document.querySelectorAll('.example')`.