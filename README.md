# Intorduction to Javascript and Interactive Charts and Graphs

## Description:
In this week, you will explore the fundamentals of JavaScript, focusing on variables, data types, functions, and manipulating the Document Object Model (DOM). Additionally, you will implement interactive charts and graphs using Chart.js. This assignment will provide hands-on experience with JavaScript programming and data visualization techniques.

## Requirements:

### JavaScript Fundamentals:
        Create an HTML file named index.html.
        Include a <script> tag to link an external JavaScript file named script.js.
        Implement JavaScript code to cover the following concepts:
            Declare variables of different data types (string, number, boolean).
            Define and call functions to perform simple operations; name them as follows:
            add
            subtract
            divide
            multiply.
            Use console.log() to print output and debug code.

### DOM Manipulation:
        Expand your index.html file to include elements for user interaction (e.g., buttons, input fields).
        Use JavaScript to manipulate the DOM in response to user actions. For example, update text content, change styles, or show/hide elements based on user input.
        Implement event listeners to handle user interactions (e.g., click events, input events).
        Ensure that your DOM manipulation code enhances the interactivity and usability of the web page.

### Interactive Charts and Graphs:
        Integrate the Chart.js library into your project by adding the necessary <script> tag to your HTML file.
        Create a canvas element in your HTML file to render the chart.

  ### Submission:
        Submit the link to your GitHub repository for evaluation, through the github classroom.







 


 
index.html
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Calculator and Chart</title>
    <script src="script.js"></script>  <script src="https://cdn.jsdelivr.net/npm/chart.js@3.9.1/dist/chart.min.js"></script>  </head>
<body>
    <h1>Interactive Calculator and Chart</h1>

    <label for="num1">Number 1:</label>
    <input type="number" id="num1">
    <br>
    <label for="num2">Number 2:</label>
    <input type="number" id="num2">
    <br>
    <button onclick="calculate()">Calculate</button>
    <p id="result"></p>

    <canvas id="myChart"></canvas>

    <script>
        // Placeholder for script.js content (functions and event listeners)
    </script>
</body>
</html>
Use code with caution.
content_copy
script.js
JavaScript
// Declare variables of different data types
let name = "John Doe";
const age = 30;
let isActive = true;

// Define functions for basic operations
function add(num1, num2) {
  return num1 + num2;
}

function subtract(num1, num2) {
  return num1 - num2;
}

function divide(num1, num2) {
  if (num2 === 0) {
    return "Error: Cannot divide by zero";
  } else {
    return num1 / num2;
  }
}

function multiply(num1, num2) {
  return num1 * num2;
}

// Function to handle calculation button click and DOM manipulation
function calculate() {
  const num1 = parseFloat(document.getElementById("num1").value);
  const num2 = parseFloat(document.getElementById("num2").value);
  
  let resultText;
  
  if (isNaN(num1) || isNaN(num2)) {
    resultText = "Please enter valid numbers";
  } else {
    resultText = `Result: ${add(num1, num2)}`;  // Call add function and display result
    
    // Prepare data for chart (example using addition result)
    const data = {
      labels: ["Addition"],
      datasets: [{
        label: "Calculation Result",
        data: [add(num1, num2)],
        backgroundColor: 'rgba(255, 99, 132, 0.2)',
        borderColor: 'rgba(255, 99, 132, 1)',
      }]
    };
    
    // Render chart using Chart.js
    const ctx = document.getElementById("myChart").getContext('2d');
    const myChart = new Chart(ctx, {
      type: 'bar',
      data: data,
      options: {}
    });
  }
  
  document.getElementById("result").innerHTML = resultText;
}

// Add event listener for button click (optional, can be placed in HTML too)
// document.getElementById("calculate").addEventListener("click", calculate);


 
 
Explanation:

This code creates two separate files: index.html and script.js.
The index.html file includes the necessary HTML structure for user interaction (input fields, buttons, and a canvas element for the chart).
It also links the external script.js file containing the JavaScript code.
The script.js file defines variables of different data types and functions for basic mathematical operations.
It includes a calculate function that handles user input from the form, performs calculations using the defined functions, and displays the result in the HTML paragraph (<p id="result"></p>).
This function also demonstrates basic error handling for non-numeric input.
In addition, it prepares data for a Chart.js bar chart based on the calculation result and renders the chart using the provided canvas element (<canvas id="myChart"></canvas>).
