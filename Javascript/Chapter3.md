# Objects

## Objects: A practical introduction

JavaScript is a prototype based Object Oriented programming language. What does this meam? We define objects which are similar to real life objects. Each object has properties which help to characterise what that object is.

Each object is an unique instance of an opbject prototype (class). 

Objects can have features to change the value of the properties called methods (functions for a patricular class).

---

## JavaScript objects: The code version

Javacript objects are collections of properties and methods that describe and act on the object.

Here is an example of a JavaScript object. The `const` is a variable that we are saving the object instance to. The object is created using the first curly brackets.

```JavaScript
const backpack = {
    name: "Everyday Backpack",
    volume:30,
    color: "grey",
    pocketNum: 15,
    strapLength: {
        left: 26,
        right: 26,
    },
    lidOpen:false,
    toggleLid:function (lidStatus){
        this.lidOpen = lidStatus;
    },
};
```
Anything can be used as the value of the key value pair inside the object including strings, ints arrays and other objects (strapLength is an example of this.)


We also have an example of a method within this object for the action of opening the lid of the backpack:
```JavaScript
toggleLid:function (lidStatus){
        this.lidOpen = lidStatus;
}
```
The method is still a key value pair, with the key being the name of the method and the value being the actual function. In this example the method name is the toggleLid. 

The `this` keyword refers to the fact that this function is acting only specifically on this  current object and no other.

---

## Object containers

Objects need somewhere to live and a name so that we can access them when required. In the previus example we used a `const` variable to contain the object. 

A constant or `const` can contain the object, and we can change the properties of the object within it, but cannot change the object that is housed within the `const` variable. This is why we use constants to house objects.

---

## Object properties

They describe attributes of a property.


## Accessing object properties

There are two main ways to access a object property:
- Dot notation
- Bracket notation

Dot notation uses a dot between the object name and the propertie name. For example:

```JavaScript
console.log(backpack.pocketNum);
```
Bracket Notation 


## Practice: Build a new object

## Object methods

## Practice: Build a new method

## Classes: Object blueprints

## Object contructors

## Practice: Build a new object with a constructor

## Global objects

## Challenge: Create a new object type

## Solution: Create a new object type



