---
title: Javascript Data Types/Lists
hide: True
description: A Tech Talk on javascript data types and how to use with lists
type: hacks
permalink: /basics/datatypes
author: Rayane Souissi
comments: True
courses: {'csp': {'week': 5}}
---

{% include nav_basics.html %}

## Hacks


```python
%%js

// Define a player object with various properties
var obj = {
    name: "Rayane",             // Player's name
    age: 17,                    // Current age of the player
    sport: "Soccer",            // Sport the player is involved in
    favoriteclass: "CSP",       // Player's favorite class
    favoritecolor: "Green",     // Player's favorite color

    // Method to compute future age of the player given a number of years
    futureAge: function(years) {
        return this.age + years;
    }
};

// Log the player's data to the console
console.log(obj);

// Calculate and log the player's age after 5 years using the futureAge method
console.log("Rayane's age after 5 years will be:", obj.futureAge(5));

// Perform a conditional arithmetic operation based on player's current age:
// - If the player's age is above 15, sum a large number with a smaller one
// - Otherwise, sum the smaller number with itself
var largeNumber = (obj.age > 15) ? 900000000000 + 90000000000 : 90000000000 + 90000000000;
console.log(largeNumber);

// Define a function to provide a descriptive type check
function displayType(value) {
    // Return a string that combines the value and its type
    return "Type of '" + value + "' is: " + typeof value;
}

// Log the type of various values using the displayType function
console.log(displayType(17));         // Display type for a number
console.log(displayType('soccer'));   // Display type for a string
console.log(displayType(true));       // Display type for a boolean
```


    <IPython.core.display.Javascript object>

