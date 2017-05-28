---
layout: post
title:  Javascript Hoisting
date:   2017-05-28 03:09:46 -0400
---


**Hoisting**, in the context of Javascript, is when all declarations are brought to the top of their current scope. Initializations on the other hand, remain unmoved on their original lines.

*What is a declaration?* A declaration is any time the keywords `var` or `function` are used. Function declarations get hoisted first, followed by variable declarations. It is good practice to write declarations at the top of their containing scopes, since this is the order that Javascripts reads code. Not doing so will make code more prone to bugs.

*What is an initialization?* An initialization is when a value is assigned to a variable.

For convenience's sake, Javascript allows us to write declarations and initializations together in the same line:

```
var color = "yellow";
```

This actually gets read by Javascript as two lines:

```
var color;  // declaration
color = "yellow";  // initialization
```

*Throwing function expressions into the mix.* We now know that function declarations by themselves automatically get hoisted up, just like variable declarations. However, what happens when a function is assigned to a variable? Suppose we had this function expression.

```
var numbers = function() {
  console.log("321");
};
```

Javascript reads this in the same way as it does for regular variables, which results in this:

```
var numbers  // declaration

numbers = function() {  // initialization
  console.log("321");
};
```

Here is a final example that combines the main principles of hoisting. We have code that looks like this:

```
(function() {
  var red = apple;
  var yellow = banana;
  var green = function() {
    return true;
  };
  function purple() {
    return true;
  }
})();
```

Following all of the rules to hoisting, Javascript will actually read the code snippet as:

```
(function() {
  function purple() {
    return true;
  }
	
  var red;
  var yellow;
  var green;
	
  red = apple;
  yellow = banana;
	
  green = function() {
    return true;
  }
})();
```

The function declaration gets hoisted up first, followed by the variable declarations, and lastly the variable initializations -- all while maintaining their current scope.
