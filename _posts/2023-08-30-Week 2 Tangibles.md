---
comments: True
layout: post
title: Week 2
description: 
type: tangibles
courses: { csp: {week: 2, categories: [4.A]} }
categories: ['C4.1']
---

**Implementation of Hacks:**

- **Forked the car sales data table, replaced the data with soccer player salaries. Used CSS to customize the table (experimented with different code online).**

- **JS Calculator - forked Mr. Mort's code, but it resulted in a column of numbers, and didn't really look like an actual calculator. So, I used 'border (adds a border for each button), 'padding (adds padding to make the button larger), 'font-size, 'text-align (centers the text), etc to make squares in the calculator that each have different numbers inside them.** 

"Liquid Exception: Could not locate the included file 'nav_home.html' in any of ["/Users/rayanesouissi/vscode/studentrep/_includes", "/private/var/folders/3r/_pbvf6d522957yhk2jxc75440000gn/T/jekyll-remote-theme-20230830-32650-5kh0fr/_includes"]. Ensure it exists in one of those directories and is not a symlink as those are not allowed in safe mode. in /Users/rayanesouissi/vscode/studentrep/_posts/2023-08-29-calculator.md"

- cd /Users/rayanesouissi/vscode/studentrep
- ls _includes
- touch _includes/nav_home.html
- ls -la _includes
- bundle exec jekyll build --verbose
- jekyll build --verbose


"Cannot read properties of null (reading 'value')"
- **This error can occur when the JavaScript code runs before the HTML DOM is fully loaded, leading to the display being null.**
- You can place the script at the end of the body tag or use a DOMContentLoaded event

"C is not defined"
- **This is because in the HTML, the button uses onclick="C()", but there is no function C() defined in JavaScript.**
- The HTML should use onclick="clearDisplay()" to match the JavaScript function name.

"Calculate is not defined"
- **If for any reason the JavaScript file did not load or there was an error above this function, the JavaScript might stop processing further, making subsequent functions like calculate() undefined**
- Fix preceding JavaScript errors to ensure that the entire script file is read and processed.

"Unexpected token"
- **Syntax errors, such as a missing bracket, can lead to this issue**
- Correct the JavaScript syntax.