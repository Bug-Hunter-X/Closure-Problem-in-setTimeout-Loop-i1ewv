# Closure Problem in setTimeout Loop in TypeScript

This repository demonstrates a common issue encountered when using `setTimeout` within a loop in JavaScript and TypeScript.  The problem stems from the way closures capture variables, leading to unexpected behavior with asynchronous operations.

## The Bug

The `printNumbers2` function aims to print numbers 1 through `n` with a slight delay using `setTimeout`. However, due to the asynchronous nature of `setTimeout`, the loop completes before the `setTimeout` callbacks have a chance to execute.  By the time the callbacks finally execute, the loop variable `i` has already reached its final value, resulting in the same value being printed multiple times.

## The Solution

The solution involves using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop. This ensures that each `setTimeout` callback captures its own copy of the loop variable `i`, preventing the closure issue.