# Incorrect NaN Comparison in TypeScript Array Comparison Function

This repository demonstrates a subtle bug in a TypeScript function designed to compare two number arrays for equality. The function fails to correctly handle `NaN` values.

## Bug Description

The `compareArrays` function uses a simple loop to compare elements at corresponding indices.  However, `NaN !== NaN` evaluates to `true` in JavaScript and TypeScript. Therefore, the function incorrectly returns `false` when comparing arrays containing `NaN` at the same index.

## How to Reproduce

1. Clone this repository.
2. Run `tsc bug.ts` to compile the TypeScript code.
3. Run `node bug.js` to execute the compiled JavaScript code.  Observe the unexpected result when comparing arrays containing `NaN`.

## Solution

The solution involves using the `Number.isNaN()` function to explicitly check for `NaN` values.  See the `bugSolution.ts` file for a corrected implementation.