---
title: HTML DOM
hide: True
description: A Tech Talk on how javascript can interact with HTML DOM
type: hacks
permalink: /basics/dom
author: Rayane Souissi
comments: true
courses: {'csp': {'week': 5}}
---

{% include nav_basics.html %}

# Hacks
- Copy your HTML code from the HTML hacks. Write a Javascript snippet to switch the links of the two a tags when a button is pressed. Once they are switched, change the inner HTML of the top p tag to the word "switched!"


```python
%%html

<style>
    @keyframes gradientBG {
        0%, 100% { background-position: 0% 50%; }
        50% { background-position: 100% 50%; }
    }

    .gradient-container {
        /* Modified gradient colors to shades of grey and black */
        background: linear-gradient(-45deg, #999, #666, #333, #000);
        background-size: 400% 400%;
        animation: gradientBG 15s ease infinite;
        padding: 20px;
        border-radius: 8px;
        color: white; /* Set text color as white for inside this container */
        font-size: 24px; 
    }

    .gradient-container a {
        display: block;
        margin-bottom: 20px;
        text-decoration: none;
    }
</style>

<p id="notification"></p>

<div class="gradient-container">
  <a id="x" href="https://www.fifa.com">Link to FIFA</a>
  <a id="y" href="https://www.manutd.com">Link to Manchester United</a>
</div>

<script>
    var linkToFIFA = document.getElementById("x");
    var linkToManUtd = document.getElementById("y");
    
    // Swap the href attributes of the two links
    [linkToFIFA.href, linkToManUtd.href] = [linkToManUtd.href, linkToFIFA.href];
    
    document.getElementById("notification").innerHTML = "switched!";
</script>

```



<!-- Simplified CSS styles -->
<style>
    @keyframes gradientBG {
        0%, 100% { background-position: 0% 50%; }
        50% { background-position: 100% 50%; }
    }

    .gradient-container {
        /* Modified gradient colors to shades of grey and black */
        background: linear-gradient(-45deg, #999, #666, #333, #000);
        background-size: 400% 400%;
        animation: gradientBG 15s ease infinite;
        padding: 20px;
        border-radius: 8px;
        color: white; /* Set text color as white for inside this container */
        font-size: 24px; 
    }

    .gradient-container a {
        display: block;
        margin-bottom: 20px;
        text-decoration: none;
    }
</style>

<p id="notification"></p>

<div class="gradient-container">
  <a id="x" href="https://www.fifa.com">Link to FIFA</a>
  <a id="y" href="https://www.manutd.com">Link to Manchester United</a>
</div>

<script>
    var linkToFIFA = document.getElementById("x");
    var linkToManUtd = document.getElementById("y");

    // Swap the href attributes of the two links
    [linkToFIFA.href, linkToManUtd.href] = [linkToManUtd.href, linkToFIFA.href];

    document.getElementById("notification").innerHTML = "switched!";
</script>


