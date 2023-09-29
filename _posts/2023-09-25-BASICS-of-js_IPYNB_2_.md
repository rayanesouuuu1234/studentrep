---
title: Basics of JS
hide: True
description: A Tech Talk on how to use javascript
type: hacks
permalink: /basics/javascript
author: Rayane Souissi
comments: True
courses: {'csp': {'week': 5}}
---

{% include nav_basics.html %}



# Hacks
- Write a JavaScript program that compares two variables, a and b. Log "a is greater" if a is greater than b, "b is greater" if b is greater than a, and "both are equal" if a and b are equal. Make sure to use if statements and console.log


```python
%%js  

// Assign the value 2 to the variable x
var x = 2;

// Assign the value 4 to the variable y
var y = 4;

// Check if the value of x is greater than the value of y
if (x > y) {
    // If x is greater than y, log this message to the console
    console.log("x is greater than y");
}

// Check if the value of y is greater than the value of x
if (y > x) {
    // If y is greater than x, log this message to the console
    console.log("y is greater than x");
} else {
    // If neither of the above conditions are met (i.e., x and y are equal), log this message
    console.log("they are equal")
}
```


    <IPython.core.display.Javascript object>

