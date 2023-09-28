---
toc: True
comments: True
layout: post
title: JS Basics Test
description: None
courses: {'csp': {'week': 6}}
type: hacks
---

```python
%%html
<div style="background-color: rgb(86, 141, 189); color: black;">
    <h3>SOCCER</h3>
    <p>Soccer has been an integral part of my life from the very beginning. Since my early days, I've been drawn to the magic of the sport, reveling in every dribble, pass, and goal. This passion drove me to not only play the game but to immerse myself in it. Having played soccer throughout my life, I've been fortunate enough to represent both my club and high school teams. These experiences have given me countless memories, life lessons, and friendships that I cherish. Now, as I play club soccer and represent my high school, I am reminded every day of why I fell in love with the sport. The camaraderie, the challenges, the exhilaration of a winning goal, and even the lessons from a loss, have shaped me as an individual. Soccer is not just a sport to me; it's a lifelong journey, a passion, and an integral part of who I am. 
        <br>
        <br>
        Wresting is fun and good for you. 

    </p>
    <a href="https://www.uefa.com/uefachampionsleague/"><button>Click if you like soccer</button></a>
</div>

```


```python
%%html
<div style='background-color: blueviolet;'>
    <a href="https://uww.org">link to wrestling</a>
    <br>
    <a href="https://www.dnhsnighthawkswrestling.com">link to DNHS wrestling</a>
</div>
```


```python
%%js
x = 2;
  y = 4;
  if (x > y) {
      console.log("x is greater than y");
  }
   if (y > x) {
      console.log("y is greater than x");
  } else {
      console.log("they are equal")
  }
```


```python
%%js
var obj = {
    name: "Timo",
    age: 15,
    sport: "Wrestling",
    favoriteclass: "CSP",
    favoritecolor: "Purple"};
console.log(obj);
console.log(5+5);
console.log(typeof 17);
console.log(typeof 'wrestling');
console.log(typeof true);
```


```python
%%js
var obj = {
    name: "Timo",
    age: 15,
    sport: "Wrestling",
    favoriteclass: "CSP",
    favoritecolor: "Purple"};
console.log(obj);
console.log(5+5);
console.log(typeof 17);
console.log(typeof 'wrestling');
console.log(typeof true);
```


    <IPython.core.display.Javascript object>



```python
%%js

var numbers = [];
var newNumbers = [];
var i = 0;

while (i < 100) {
    numbers.push(i);
    i += 1;
}
for (var i of numbers) {
    if (numbers[i] % 5 === 0)
        newNumbers.push(numbers[i]);
    if (numbers[i] % 2 === 0)
        newNumbers.push(numbers[i]);
}
console.log(newNumbers);
```


```python
%%js

var alphabet = "abcdefghijklmnopqrstuvwxyz";
var alphabetList = [];

for (var i = 0; i < 25; i++) {
    alphabetList.push(i);
}

console.log(alphabetList);
```
