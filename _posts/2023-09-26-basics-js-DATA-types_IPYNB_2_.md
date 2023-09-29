---
title: Javascript Data Types/Lists
hide: True
description: A Tech Talk on javascript data types and how to use with lists
type: hacks
permalink: /basics/datatypes
author: Rayane Souissi
courses: {'csp': {'week': 5}}
---

{% include nav_basics.html %}

## Hacks


```python
%%js

// Define an object 'obj' with various properties and values.
var obj = {
    name: "Rayane",
    age: 17,
    sport: "Soccer",
    favoriteClass: "CSP",
    favoriteColor: "green"
};

// Log the object to the browser console.
console.log(obj);

// Define a sample array of numbers for which we'll calculate the standard deviation.
var numbers = [10, 20, 30, 40, 50];

// Define a function to calculate the standard deviation for an array of numbers.
function standardDeviation(arr) {
    // Calculate the number of elements in the array.
    const n = arr.length;
    
    // Calculate the mean (average) of the numbers.
    const mean = arr.reduce((a, b) => a + b) / n;
    
    // Calculate the variance by subtracting the mean and squaring the result for each number.
    // Then find the mean of those squared differences.
    // Finally, the square root of that result gives the standard deviation.
    return Math.sqrt(arr.map(x => Math.pow(x - mean, 2)).reduce((a, b) => a + b) / n);
}

// Display the calculated standard deviation in the Jupyter notebook output.
element.append("Standard Deviation of numbers: " + standardDeviation(numbers));

// Log the type of various data values to the browser console.
console.log(typeof 42);          // Expected output: "number"
console.log(typeof 'soccer');    // Expected output: "string"
console.log(typeof true);        // Expected output: "boolean"
```


    <IPython.core.display.Javascript object>

