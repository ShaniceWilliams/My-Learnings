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

**Dot notation** uses a dot between the object name and the property name. THis is the preferred method for referring to object properties. For example:

```JavaScript
console.log("The poketNum value: ", backpack.pocketNum);
```
**Bracket Notation** uses square brackets to refer to an object property. This can be used when the property name is not standard (for instance has a space). Here is an example:
```JavaScript
console.log("The poketNum value: ", backpack["pocketNum"]);
```
This can also be used when the value of a variable is an object property:
```JavaScript
var query = "pocketNum"
console.log("The poketNum value: ", backpack[query]);
```
This allows for more flexibility as we could not use dot notation for that variable.

---

## Practice: Build a new object

Task:
  - Create JavaScript objects based on objects in your current environment.
  - Give each object an identifiable name.
  - Create properties to describe the objects and set their values.
  - Find an object that has another object inside of it to create a nested object.
  - Test your objects in the browser console by accessing the entire object and its specific properties.

Here was my examples of creating a laptop object and a pen holder object:
```Javascript
const laptop = {
    name: "Microsoft Surface 8",
    screenSize: 13,
    processor: "Intel i7 11th gen",
    ramSize: "16",
    storage: 256,
    storageUnit: "gb",
    colour:"black",
    kbAttached: false,
    attachKb: function (kbStatus) {
    this.kbAttached = kbStatus;
  },
};
console.log(laptop.ramSize, laptop.storageUnit)

const penHolder = {
    matieral: "wood",
    capacity: 20,
    currentFillLevel: 50,
    pens: {
        ballpoint : {
            inkColor: "black"
        },
        fountainPen: {
            inkColor: "Blue",
            cartridgesLeft: 5
        }
    }
};
 
console.log(penHolder.pens.fountainPen)
```

---

## Object methods

Functions within objects typically perform actions on the properties of the object. When fucntiosn are inside an object, they are called methods.

There are two ways that a function can be called as can be seen below, however the convention is to use the first method as this is more readable and it leaves less room for interpretation.

```JavaScript
toggleLid: function (lidStatus) {
    this.lidOpen = lidStatus;
  },

toggleLid(lidStatus) {
    this.lidOpen = lidStatus;
  },
```
Within the parentheses we can see `lidStatus` which is the parameter for this method. THis means that when we want to call the method to make a change to toggle the lid, we will need to provide that data within the fucntion call, for the change to be made.

Here is an example of the methods being called:

```JavaScript
toggleLid(true);

backpack.newStraplength(10,15);
```
In the second example this method required two parameters, as there is a strap length for left and right.

---

## Practice: Build a new method

Task:
  - Create a method for each object property.
  - The method receives a value to match the property to be changed.
  - Create a simple function to replace the current property value with the received value.
  - Test the method by sending new values and checking the properties in the console.

```JavaScript
const backpack = {
  name: "Everyday Backpack",
  volume: 30,
  color: "grey",
  pocketNum: 15,
  strapLength: {
    left: 26,
    right: 26,
  },
  toggleLid: function (lidStatus) {
    this.lidOpen = lidStatus;
  },
  newStrapLength: function (lengthLeft, lengthRight) {
    this.strapLength.left = lengthLeft;
    this.strapLength.right = lengthRight;
  },
  updateName: function(newName) {
    this.name = newName;
  },
  updateVolume: function(newVolume) {
    this.volume = newVolume;
  },
  updateColor: function(newColor) {
    this.color = newColor;
  },
  updatePocketNum: function(newPocketNum) {
    this.pocketNum = newPocketNum;
  },
};
```

---

## Classes: Object blueprints

Classes are blueprints for making objects that share the same properties and methods.

To create a class first we use either a class declaration or class expression:
```JavaScript
/*Class Declaration*/
class NameOfCLass {}

/*Class Expression*/
const NameOfCLass = class {}

```
There is no real difference between the two, just preference. Most use the expression, but in the example provided, declaration is used.

There are 3 main steps when creating a class:
  1. Define the parameters
  2. Define the properties
  3. Outline any methods

```JavaScript
class Backpack {
    constructor(
        //Defines parameters
        name,
        volume,
        color,
        pocketNum,
        strapLengthL,
        strapLengthR,
        lidOpen
    ) {
        //Define Properties
        this.name = name;
        this.volume = volume;
        this.color = color;
        this.pocketNum = pocketNum;
        this.strapLength = {
            left: strapLengthL,
            right: strapLengthR,
        };
        this.lidOpen = lidOpen;
    }
    //Add method to class
    toggleLid: function (lidStatus) {
        this.lidOpen = lidStatus;
  }
    newStrapLength: function (lengthLeft, lengthRight) {
        this.strapLength.left = lengthLeft;
        this.strapLength.right = lengthRight;
  }
}

```

To create a new object based on the class we have created, we have to create a new constant and the `new` keyword with the data that we want for each parameter as below. Once the object is created we can access the properties as we have in previous examples.
```JavaScript
const everydayPack = new Backpack(
    "Everyday Backpack",
    30,
    "grey",
    15,
    25,
    25,
    false
);

console.log("The everydayPack object:", everydayPack);
console.log("Number of pockets:", everydayPack.pocketNum);
```
Classes are usually created in a seperate file and then imported into the file where the object is to be created to reduce the chance of trying to create an object without the class being ready.

---

## Object contructors

Object constructors are another shorter and less advanced way to create objects when compared to classes. This is a function. the main way this is different to the lass is that the methods are contained within the constructing functionn alongside the properties as can be seen in the below example:

```JavaScript
function Backpack(
  name,
  volume,
  color,
  pocketNum,
  strapLengthL,
  strapLengthR,
  lidOpen
) {
  this.name = name;
  this.volume = volume;
  this.color = color;
  this.pocketNum = pocketNum;
  this.strapLength = {
    left: strapLengthL,
    right: strapLengthR,
  };
  this.lidOpen = lidOpen;
  this.toggleLid = function (lidStatus) {
    this.lidOpen = lidStatus;
  };
  this.newStrapLength = function (lengthLeft, lengthRight) {
    this.strapLength.left = lengthLeft;
    this.strapLength.right = lengthRight;
  };
}
```
To construct a new object based oin this is dopne in the same was as you would when creating a class.

Classes offer more flecxibility and capabilities, but older code may contain this constructor functions.

---
## Practice: Build a new object with a constructor

Task: Making classes and objects
  - Find a type of object you have more than one of in your house (eg. clothing, writing tools, etc).
  - Create a class describing this object type - its properties and methods.
  - Create several objects using the class.
  - Test the objects by calling their properties and using their methods in the console.

```JavaScript

```

---
## Global objects

## Challenge: Create a new object type

## Solution: Create a new object type



