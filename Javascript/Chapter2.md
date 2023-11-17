# Up and Running with JS

## Javascript in a HTML document

Where does it live?
- Inline in the html document
- in an external js file.

JS within an HTML document is usually at the end of the body within a `<script>` tag. Though it can be entered anywhere in the document.

It's preferential to have it at the end as this means that all of the HTML will have been rendered by the browser. That way, if the JS has to interact with HTML elements there is no risk that the element hasn't been rendered yet, as that would cause problems.

This is not the modern way to render js.

---

## JavaScript as an external file

In most cases we would handle the JS in the same way as CSS. Having the JS in a seperate file and adding a reference to that file into the html file.

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Module demo</title>
    <script src="script.js"></script>
  </head>
  <body></body>
</html>
```
Here is an example of how the `script.js` file is referred to in the head section within `script` tags. This specific case will cause an error as it is referred to before the body section. As this script refers to a body element and that has not yet rendered, this causes an error in the console.

To fix this error we would neeed to move the reference to below the body element as below:
```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Module demo</title>
  </head>
  <body></body>
  <script src="script.js"></script>
</html>
```

---

## Modern JavaScript Loading

In the previous section, we discussed why it is not alway possible to reference the js file in the head element of the html file. HTML files are rendered by browsers from top to bottom, and if the js file is at the top there may be elements of the file that are depending on elements in the html that have not rendered yet, causing errors. 

![img](images\Default%20rendering.png)

However in real world examples it will be more common that there will be parts of the js that will need to be executed at various points throughout the rendering of the html file.

This is where keywords `async` and `defer` come in.

### Async

![img](images\async_render.png)

### Defer

![img](images\defer_render.png)

Best practice is to use async and defer to load javascript.


---

## JavaScript Modelling

Modules allow us to import parts of code to make code easier to understand and manage. Makes the code more reusuable.

To get this to work you will need three components.

1. export statement at the end of a module.

```JavaScript
export default backpack;
```
2. import statement to be able to use the functionality of the module into the second script.
```JavaScript
import backpack from "./backpack.js";
```
3. For the module to work together, both files need to be referred to in the HTML file. They are given the type module, which automatically means that they will follow defer loading.
```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Module demo</title>
    <script type="module" src="backpack.js"></script>
    <script type="module" src="script.js"></script>
  </head>
  <body></body>
</html>
```

This is a standard way of working with most JavaScript frameworks.

It is also worth noting that using this method means that objects are only availiable within the scope of the script that you are importing the module into, and so cannot be accessed in the console in the same way as previous examples.

This is worth considering when looking to build modules that it may not be the best idea to house objects within a module, but in the main file.


