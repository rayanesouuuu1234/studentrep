---
layout: post
hide: True
title: Basics of HTML Guide
description: An introduction to basic HTML, and resources to learn more.
type: hacks
permalink: /basics/html
author: Rohan Juneja
courses: {'csp': {'week': 5}}
---

{% include nav_basics.html %}


# How does HTML work?
Similar function to Markdown, syntax defines how stuff should be displayed
- HTML is based on beginning and closing tags `<tagname>content</tagname>`
  - Note the "/" on the ending or closing tag of the pair

## Compare markdown to html below
This below example shows comparison of a [heading](https://www.w3schools.com/html/html_headings.asp) and [paragraph](https://www.w3schools.com/html/html_paragraphs.asp).  Click on links to see many more HTML examples.


```python
%%html

<h3>HTML: This is a Heading</h3>
<p>This is a paragraph.</p>
```



<h3>HTML: This is a Heading</h3>
<p>This is a paragraph.</p>



# Attributes
- Learn about [attributes](https://www.w3schools.com/html/html_attributes.asp) 
- Tags can have additional info in the form of attributes
- Attributes usually come in name/value pairs like: name="value"

```html
<tagname attribute_name="attribute_value" another_attribute="another_value">inner html text</tagname>
```

- href example with attribute for web link and inner html to describe link

```html
<a href="https://www.w3schools.com/html/default.asp">Visit W3Schools HTML Page</a>
```

## Sample Markdown vs HTML Tags
Image Tag - Markdown

```md
![describe image](link to image)
```

Image Tag - HTML

```html
<!-- no content so no end tag, width/height is optional (in pixels) -->
<img alt="describe image" src="link to image" width="100" height="200">
```

Link Tag - Markdown

```md
[link text](link)
```

Link Tag - HTML

```html
<a href="link">link text</a>
```

Bolded Text - Markdown

```md
**Bolded Text**
```

Bolded Text - HTML

```md
<strong>Bolded Text</strong>
```

Italic Text - Markdown

```md
*Italic Text*
```

Italic Text - HTML

```md
<i>Italic Text</i>
```

# More tags (not really in markdown)
P tag (just represeants a paragraph/normal text)

```html
<p>This is a paragraph</p>
```

Button

```html
<button>some button text</button>
```

Div (groups together related content)

```html
<!-- first information -->
<div>
    <!-- notice how tags can be put INSIDE eachother -->
    <p>This is the first paragarph of section 1</p>
    <p>This is the second paragraph of section 1</p>
</div>

<!-- second information -->
<div>
    <!-- notice how tags can be put INSIDE eachother -->
    <p>This is the first paragarph of section 2</p>
    <p>This is the second paragraph of section 2</p>
</div>
```



# Resources
- https://www.w3schools.com/html/default.asp
- I will show a demo of how to find information on this website

# HTML Hacks
- Below is a wireframe for an HTML element you will create. A wireframe is a rough visual representation of HTML elements on a page and isn't necessarily to scale or have the exact styling that the final HTML will have. Using the syntax above, try to create an HTML snippet that corresponds to the below wireframe.
- The "a tags" can contain any links that you want

![wireframe for html hacks]({{ site.baseurl }}/images/wireframe.png)

## WIREFRAME 1


```python
%%html

<!-- Embed Google Fonts to use in the HTML for typography -->
<link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">

<!-- Start of the main content -->
<div style="background-color: rgb(0, 51, 96); color: rgb(255, 255, 255); font-family: 'Pacifico', cursive;">

    <h3>SOCCER</h3>
    
    <!-- Use the Roboto font for the paragraph for better readability -->
    <p style="font-family: 'Roboto', sans-serif;">
        Soccer has been an integral part of my life from the very beginning. Since my early days, I've been drawn to the magic of the sport, reveling in every dribble, pass, and goal. This passion drove me to not only play the game but to immerse myself in it. Having played soccer throughout my life, I've been fortunate enough to represent both my club and high school teams. These experiences have given me countless memories, life lessons, and friendships that I cherish. Now, as I play club soccer and represent my high school, I am reminded every day of why I fell in love with the sport. The camaraderie, the challenges, the exhilaration of a winning goal, and even the lessons from a loss, have shaped me as an individual. Soccer is not just a sport to me; it's a lifelong journey, a passion, and an integral part of who I am. 
        <br>
        <br>
        (FC Barcelona is winning the Champions League this season) 
    </p>

    <a href="https://www.uefa.com/uefachampionsleague/">
        <button>Click for more about soccer</button>
    </a>
</div>
```



<!-- Embed Google Fonts to use in the HTML for typography -->
<link href="https://fonts.googleapis.com/css2?family=Pacifico&display=swap" rel="stylesheet">

<!-- Start of the main content -->
<div style="background-color: rgb(0, 51, 96); color: rgb(255, 255, 255); font-family: 'Pacifico', cursive;">

    <h3>SOCCER</h3>

    <!-- Use the Roboto font for the paragraph for better readability -->
    <p style="font-family: 'Roboto', sans-serif;">
        Soccer has been an integral part of my life from the very beginning. Since my early days, I've been drawn to the magic of the sport, reveling in every dribble, pass, and goal. This passion drove me to not only play the game but to immerse myself in it. Having played soccer throughout my life, I've been fortunate enough to represent both my club and high school teams. These experiences have given me countless memories, life lessons, and friendships that I cherish. Now, as I play club soccer and represent my high school, I am reminded every day of why I fell in love with the sport. The camaraderie, the challenges, the exhilaration of a winning goal, and even the lessons from a loss, have shaped me as an individual. Soccer is not just a sport to me; it's a lifelong journey, a passion, and an integral part of who I am. 
        <br>
        <br>
        (FC Barcelona is winning the Champions League this season) 
    </p>

    <a href="https://www.uefa.com/uefachampionsleague/">
        <button>Click for more about soccer</button>
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


