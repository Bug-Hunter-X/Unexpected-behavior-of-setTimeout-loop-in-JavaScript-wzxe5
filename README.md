# Unexpected setTimeout Loop Behavior in JavaScript

This repository demonstrates a common issue encountered when using `setTimeout` within a loop in JavaScript. The problem arises from how closures and variable scoping work in JavaScript.

## The Bug

The `bug.js` file contains a function `myFunc` that uses a `for` loop to schedule multiple `setTimeout` calls.  Intuitively, you might expect the loop to print values from 0 to 9 with a one-second delay between each. However, due to how closures work, it actually prints the final value of `i` (which is 10) ten times. 

## The Solution

The `bugSolution.js` file demonstrates the correct way to achieve the intended behavior.  It uses an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, capturing the value of `i` correctly.

## How to Run

1. Clone this repository.
2. Open `bug.js` and `bugSolution.js` in your favorite JavaScript environment (e.g., a browser's console, Node.js).
3. Run the `myFunc` function in both files and observe the difference in the output. 