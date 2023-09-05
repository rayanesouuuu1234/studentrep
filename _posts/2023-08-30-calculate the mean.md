---
comments: True
layout: post
title: Rayane's Mean Calculator
description: 
type: hacks
courses: { csp: {week: 2, categories: [4.A]} }
categories: ['C4.1']
---
<html>
<head>
    <style>
        #container {
            margin: 50px;
        }
    </style>
</head>
<body>
    <!-- Calculator UI -->
    <div id="container">
        <h1>Mean Calculator</h1>
        <form id="numberForm">
            <input type="text" id="numbers" placeholder="e.g., 1,2,3,4,5">
            <button type="submit">Calculate Mean</button>
        </form>
        <p id="result"></p>
    </div>

    <!-- JavaScript Code -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const form = document.getElementById('numberForm');
            const result = document.getElementById('result');

            form.addEventListener('submit', function(event) {
                event.preventDefault();
                const numbers = document.getElementById('numbers').value.split(',').map(Number);

                if (numbers.some(isNaN)) {
                    result.textContent = 'Please enter a valid list of numbers separated by commas.';
                    return;
                }

                const sum = numbers.reduce((acc, val) => acc + val, 0);
                const mean = sum / numbers.length;
                result.textContent = `The mean is: ${mean}`;
            });
        });
    </script>

    <!-- Explanations of Specific Code Commands -->
    <div id="explanations">
        <h3>New Insights</h3>
        <ul>
            <li><code>document.addEventListener('DOMContentLoaded', () => { ... })</code>: Waits for the HTML document to be completely loaded before running the JavaScript code inside.</li>
            <li><code>const form = document.getElementById('numberForm');</code>: Fetches the form element with the id 'numberForm'.</li>
            <li><code>const result = document.getElementById('result');</code>: Fetches the paragraph element with the id 'result'.</li>
            <li><code>form.addEventListener('submit', function(event) { ... })</code>: Adds a 'submit' event listener to the form. When the form is submitted, the code inside this function will execute.</li>
            <li><code>event.preventDefault();</code>: Prevents the default submit action of the form, which would cause the page to reload.</li>
            <li><code>const numbers = document.getElementById('numbers').value.split(',').map(Number);</code>: Fetches the value from the input field, splits it by commas, and maps each entry to a number.</li>
            <li><code>if (numbers.some(isNaN)) { ... }</code>: Checks if any of the entries are not a number (NaN). If so, an error message is displayed.</li>
            <li><code>const sum = numbers.reduce((acc, val) => acc + val, 0);</code>: Calculates the sum of all the numbers in the array.</li>
            <li><code>const mean = sum / numbers.length;</code>: Calculates the mean by dividing the sum by the total number of entries.</li>
            <li><code>result.textContent = `The mean is: ${mean}`;</code>: Outputs the mean to the paragraph element with the id 'result'.</li>
        </ul>
    </div>
</body>
</html>
