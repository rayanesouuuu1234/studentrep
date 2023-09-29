---
layout: post
hide: True
title: Basics of HTML
description: An introduction to basic HTML, and resources to learn more.
type: hacks
permalink: /basics/html
author: Rayane Souissi
comments: true
courses: {'csp': {'week': 5}}
---

{% include nav_basics.html %}

## WIREFRAME 1


```python
%%html

<!-- Embed Google Fonts to use in the HTML for typography -->
<link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500&display=swap" rel="stylesheet">

<!-- Start of the main content -->
<div style="background-color: rgb(0, 51, 96); color: rgb(255, 255, 255); font-family: 'Pacifico', cursive; padding: 20px;">

    <h3>SOCCER</h3>
    
    <!-- Use the Roboto font for the paragraph for better readability -->
    <p style="font-family: 'Roboto', sans-serif; line-height: 1.6; margin-bottom: 20px;">
        Soccer has been an integral part of my life from the very beginning. Since my early days, I've been drawn to the magic of the sport, reveling in every dribble, pass, and goal. This passion drove me to not only play the game but to immerse myself in it. Having played soccer throughout my life, I've been fortunate enough to represent both my club and high school teams. These experiences have given me countless memories, life lessons, and friendships that I cherish. Now, as I play club soccer and represent my high school, I am reminded every day of why I fell in love with the sport. The camaraderie, the challenges, the exhilaration of a winning goal, and even the lessons from a loss, have shaped me as an individual. Soccer is not just a sport to me; it's a lifelong journey, a passion, and an integral part of who I am. 
        <br>
        <br>
        (FC Barcelona is winning the Champions League this season) 
    </p>

    <!-- Link to UEFA Champions League website -->
    <a href="https://www.uefa.com/uefachampionsleague/" style="text-decoration: none;">
        <button style="background-color: rgb(255, 255, 255); color: rgb(0, 51, 96); font-family: 'Roboto', sans-serif; padding: 10px 15px; border: none; border-radius: 5px; cursor: pointer; transition: background-color 0.3s ease;">
            Click for more about soccer
        </button>
    </a>
</div>

```



<!-- Embed Google Fonts to use in the HTML for typography -->
<link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500&display=swap" rel="stylesheet">

<!-- Start of the main content -->
<div style="background-color: rgb(0, 51, 96); color: rgb(255, 255, 255); font-family: 'Pacifico', cursive; padding: 20px;">

    <h3>SOCCER</h3>

    <!-- Use the Roboto font for the paragraph for better readability -->
    <p style="font-family: 'Roboto', sans-serif; line-height: 1.6; margin-bottom: 20px;">
        Soccer has been an integral part of my life from the very beginning. Since my early days, I've been drawn to the magic of the sport, reveling in every dribble, pass, and goal. This passion drove me to not only play the game but to immerse myself in it. Having played soccer throughout my life, I've been fortunate enough to represent both my club and high school teams. These experiences have given me countless memories, life lessons, and friendships that I cherish. Now, as I play club soccer and represent my high school, I am reminded every day of why I fell in love with the sport. The camaraderie, the challenges, the exhilaration of a winning goal, and even the lessons from a loss, have shaped me as an individual. Soccer is not just a sport to me; it's a lifelong journey, a passion, and an integral part of who I am. 
        <br>
        <br>
        (FC Barcelona is winning the Champions League this season) 
    </p>

    <!-- Link to UEFA Champions League website -->
    <a href="https://www.uefa.com/uefachampionsleague/" style="text-decoration: none;">
        <button style="background-color: rgb(255, 255, 255); color: rgb(0, 51, 96); font-family: 'Roboto', sans-serif; padding: 10px 15px; border: none; border-radius: 5px; cursor: pointer; transition: background-color 0.3s ease;">
            Click for more about soccer
        </button>
    </a>
</div>




```python
%%html

<!-- Embed Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">

<div style="background-color: rgb(20, 0, 93); padding: 20px; border-radius: 10px;">

    <!-- Styled link with a brighter color, font changes, and some padding for visual separation -->
    <a href="https://www.dummies.com/article/home-auto-hobbies/sports-recreation/soccer/soccer-for-dummies-cheat-sheet-208057/" 
       style="color: rgb(255, 255, 255); font-family: 'Roboto', sans-serif; font-weight: 700; text-decoration: none; padding: 10px; display: block;">
        A quick guide to learning soccer
    </a>

    <!-- Styled link similar to the above -->
    <a href="https://delnorte.powayusd.com/apps/pages/teams" 
       style="color: rgb(255, 255, 255); font-family: 'Roboto', sans-serif; font-weight: 700; text-decoration: none; padding: 10px; display: block;">
        Link to DNHS soccer
    </a>

</div>

```



<!-- Embed Google Fonts to use in the HTML for typography -->
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">

<div style="background-color: rgb(20, 0, 93); padding: 20px; border-radius: 10px;">

    <!-- Styled link with a brighter color, font changes, and some padding for visual separation -->
    <a href="https://www.dummies.com/article/home-auto-hobbies/sports-recreation/soccer/soccer-for-dummies-cheat-sheet-208057/" 
       style="color: rgb(255, 255, 255); font-family: 'Roboto', sans-serif; font-weight: 700; text-decoration: none; padding: 10px; display: block;">
        A quick guide to learning soccer
    </a>

    <!-- Styled link similar to the above -->
    <a href="https://delnorte.powayusd.com/apps/pages/teams" 
       style="color: rgb(255, 255, 255); font-family: 'Roboto', sans-serif; font-weight: 700; text-decoration: none; padding: 10px; display: block;">
        Link to DNHS soccer
    </a>

</div>


