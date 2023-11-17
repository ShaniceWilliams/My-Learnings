# Chapter 1 - A Brief Introduction
These notes are based on the Javascript Essential Training Course on Linkedin Learning with Morten Rand-Hendriksen.

## Navigating the JS Landscape

It can be very conflusing seeing all of the different frameworks and knowing what to learn first. It is essential in how the internet works.

At the core is JavaScript which is a scripting language for the web. Everything else is built on this.

ECMAScript is the browser specification of the JavaScript Language. It defines how browsers should interpret the language.

TypeScript is a variation of JavaScript which has strong typing.

React, Vue, and Angular are frameworks that allow for writing JS based front end applications in a more efficient and streamlined way.

Node.js is a javascript server runtime environment user to run javascript everywhere. 

-----

## Tools for working with JavaScript

Checklist:
- Modern browser
- Code editor (such as VS code)
- Live Server environment
- The browser console

-----

## Liniting and formatting

As formatting is important to correct whilst coding Javascript, we use the following extensions to reduce error:

- Prettier helps automatically format the code.
- ESLint automatically detects coding errors and fixes them automatically.

Both of these extensions require Node.js to function. To install, navigate to [nodejs.org](https://nodejs.org) and follow the installation settings there. 

To confirm if you already have node installed, you can type the following into your terminal:
```cmd
node -v
```
Once Node has been installed you will then navigate back to the terminal and type 

```cmd
npm install
```
This will install any dependencies required for prettier and ESLint to work.

---

## Getting to know the browser console

Within the console we can access all of the functions and attributes of the objects in our code base to make changes and utilise the dynamic nature of the webpage based on how it was coded.

We can use the live server functionality to open the script.js file in the browser. From there we can right click and select inspect to see the browser tools and then access the console from there.

To access the html of the page in the console we can type `window.document`. Within this particular script.js file there was one `backpack` object, which we can access in the console by typing it's name. The console will then return and attributes or functions associated with that object.

![img](images/window%20dot%20document.png)

![img](images/backpack%20object.png)

To use nay functions for that object we type the `objectName.fucntionName(parameter)`. So in this example we were using the function toggleLid which required the parameter of the state we want to change the lid to (from False to True).

``` JavaScript
backpack.toggleLid(true)
```
Following this, the console returns the following statement as per the function: _"Lid status changed"_.

![img](images/backpack%20toggle%20lid.png)

---

## JavaScript Language basics

The browser will read your code from top to bottom, so consider this when creating variables and functions - order is important.

<u>**Comments**</u>

This is how we can leave comments:

```Javascript

// this is a single line comment

/*
This is a multiline comment.
*/
```

We can also use these commenting features to help with debugging parts of the code, by deactivating part of the code.

<u>**Semi Colons**</u>

Semi colons are often used at the end of declarations. This is not required for JS to work and is more preference. If using extensions such as Prettier and ESLint, they will add them as standard for you.

<u>**Quotation Marks**</u>

Like with semi-colons, the types of quotation marks is preference. However it is best practice to be consistent with whichever you choose.

---
