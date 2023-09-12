---
toc: false
comments: false
layout: post
title: Rayane's JS Calculator
description: Calculator
type: hacks
courses: { csp: {week: 2, categories: [4.A]} }
categories: [C1.4]
---

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculator</title>
  <style>
    /* Styles for calculator layout */
    .calculator-container {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
    }
    .calculator-output {
      grid-column: span 4;
      grid-row: span 1;
    }
    .calculator-number,
    .calculator-operation,
    .calculator-clear,
    .calculator-equals {
      border: 1px solid #ccc;
      padding: 20px;
      font-size: 20px;
      text-align: center;
      cursor: pointer;
    }

  </style>
</head>
<body>
  <!-- Container for animations -->
  <div id="animation">
    <!-- Calculator UI elements -->
    <div class="calculator-container">
      <!-- Result Display -->
      <div class="calculator-output" id="output">0</div>
      <!-- Number Buttons (0-9, decimal) -->
      <div class="calculator-number">1</div>
      <div class="calculator-number">2</div>
      <div class="calculator-number">3</div>
      <div class="calculator-operation">+</div>
      <div class="calculator-number">4</div>
      <div class="calculator-number">5</div>
      <div class="calculator-number">6</div>
      <div class="calculator-operation">-</div>
      <div class="calculator-number">7</div>
      <div class="calculator-number">8</div>
      <div class="calculator-number">9</div>
      <div class="calculator-operation">*</div>
      <div class="calculator-clear">A/C</div>
      <div class="calculator-number">0</div>
      <div class="calculator-number">.</div>
      <!-- Division Button -->
      <div class="calculator-operation">/</div> 
      <!-- Equals Button -->
      <div class="calculator-equals">=</div>
    </div>
  </div>
  <!-- JavaScript (JS) implementation of the calculator. -->
  <script>
    // Initialize important variables to manage calculations
    var firstNumber = null; // Store the first number in a calculation
    var operator = null;   // Store the operator (+, -, *, /)
    var nextReady = true;  // Track if the next input should be a new number

    // Obtain references to HTML elements
    const output = document.getElementById("output");
    const numbers = document.querySelectorAll(".calculator-number");
    const operations = document.querySelectorAll(".calculator-operation");
    const clear = document.querySelectorAll(".calculator-clear");
    const equals = document.querySelectorAll(".calculator-equals");

    // Number buttons listener
    numbers.forEach(button => {
      button.addEventListener("click", function() {
        number(button.textContent); // Call the number function with the button value
      });
    });


    function number(value) {
      if (value != ".") {
        if (nextReady == true) {
          output.innerHTML = value;
          if (value != "0") {
            nextReady = false;
          }
        } else {
          output.innerHTML = output.innerHTML + value;
        }
      } else {
        if (output.innerHTML.indexOf(".") == -1) {
          output.innerHTML = output.innerHTML + value;
          nextReady = false;
        }
      }
    }

    // Operation buttons listener
    operations.forEach(button => {
      button.addEventListener("click", function() {
        operation(button.textContent); // Call the operation function with the button value
      });
    });

    // Operator action
    function operation(choice) {
      if (firstNumber == null) {
        firstNumber = parseFloat(output.innerHTML); // Store the first number
        nextReady = true;
        operator = choice; // Store the operator (+, -, *, /)
        return;
      }
      firstNumber = calculate(firstNumber, parseFloat(output.innerHTML)); // Perform calculations
      operator = choice; // Store the new operator
      output.innerHTML = firstNumber.toString();
      nextReady = true;
    }

    // Calculator
    function calculate(first, second) {
      let result = 0;
      switch (operator) {
        case "+":
          result = first + second;
          break;
        case "-":
          result = first - second;
          break;
        case "*":
          result = first * second;
          break;
        case "/":
          if (second !== 0) {
            result = first / second; // Perform division
          } else {
            alert("Division by zero is not allowed.");
            clearCalc();
          }
          break;
        default:
          break;
      }
      return result;
    }

    // Equals button listener
    equals.forEach(button => {
      button.addEventListener("click", function() {
        equal();
      });
    });

    // Equal action
    function equal() {
      if (operator !== null) {
        firstNumber = calculate(firstNumber, parseFloat(output.innerHTML));
        output.innerHTML = firstNumber.toString();
        nextReady = true;
        operator = null;
      }
    }

    // Clear button listener
    clear.forEach(button => {
      button.addEventListener("click", function() {
        clearCalc();
      });
    });

    // A/C action
    function clearCalc() {
      firstNumber = null;
      operator = null;
      output.innerHTML = "0";
      nextReady = true;
    }
  </script>
  <!--
  Vanta animations just for fun, load JS onto the page
  -->
  <script src="/teacher/assets/js/three.r119.min.js"></script>
  <script src="/teacher/assets/js/vanta.halo.min.js"></script>
  <script src="/teacher/assets/js/vanta.birds.min.js"></script>
  <script src="/teacher/assets/js/vanta.net.min.js"></script>
  <script src="/teacher/assets/js/vanta.rings.min.js"></script>
  <script>
    // Setup Vanta scripts as functions
    var vantaInstances = {
      halo: VANTA.HALO,
      birds: VANTA.BIRDS,
      net: VANTA.NET,
     