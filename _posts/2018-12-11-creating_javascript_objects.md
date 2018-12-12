---
layout: post
title:      "Creating JavaScript Objects"
date:       2018-12-11 10:57:58 -0400
permalink:  creating_javascript_objects
---

Jim Cooper's [JavaScript Objects and Prototypes](https://app.pluralsight.com/library/courses/javascript-objects-prototypes/table-of-contents) course on Pluralsight teaches the in-depth, behind-the-scenes details of creating JavaScript objects, manipulating properties, and using prototypal inheritance. Here are my notes from the first section of the video series, called "Creating JavaScript Objects".

## Creating JavaScript Objects
Here are two different ways of creating objects--using object literals and using constructor functions with the new keyword.
### Object Literal
```
cat = {
    name: ‘Fluffy’, 
    color: ‘White’
};

console.log(cat);
```
### Constructor function
```
function Cat() { 
    this.name = ‘Fluffy’,
    this.color = ‘White’ 
};

var cat = new Cat();
console.log(cat);
```
Object literals and constructor functions are syntactic sugar for `Object.create()`
```
var cat = Object.create(Object.prototype,
    { 
        name: { 
            value: ‘Fluffy’, 
            enumerable:true, 
            writable:true, 
            configurable:true 
        },
        color: { 
            value: ‘White’, 
            enumerable:true, 
            writable:true, 
            configurable:true
        }
    });
    
console.log(cat);
```
### Strict mode
Strict mode causes JavaScript to throw errors in places that would, otherwise, just silently fail. Strict mode disallows the use of deprecated parts of JavaScript.

### This
The `this` keyword refers to an object. That object is whatever object is executing the current bit of code. By default, that is the global object. In a web browser, that is the window object.

### Creating Objects Using ES6 Classes
This is also syntactic sugar on top of existing object creation functionality.
```
class Cat {
    constructor(name, color) {
        this.name = name,
        this.color = color
    }
    
    speak() {
        display('Meeooow')
    }
}

var cat = new Cat('Fluffy', 'White');
console.log(cat);
cat.speak();
```
