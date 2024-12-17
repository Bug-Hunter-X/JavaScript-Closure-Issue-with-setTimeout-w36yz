# JavaScript Closure Issue with setTimeout

This repository demonstrates a common issue related to closures in JavaScript when using `setTimeout` within a loop.  The problem arises because the closure does not capture the value of `i` at the time of function execution, but rather references the variable itself.  Therefore, by the time `setTimeout` finally executes the callback, the loop may have already completed, and the value of `i` will be its final value.

## How to Reproduce

Clone this repository and run `bug.js`. You'll notice that the output is '10' ten times, instead of 0 through 9.

## Solution

The `bugSolution.js` file provides a solution using an immediately invoked function expression (IIFE) to create a new scope for each iteration, capturing the correct value of `i`. 