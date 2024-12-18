# React setInterval Memory Leak

This repository demonstrates a common error in React: using `setInterval` within a `useEffect` hook without proper cleanup. This leads to memory leaks and unexpected behavior.  The `bug.js` file contains the flawed code, while `bugSolution.js` provides a corrected version.

## Problem
The `setInterval` function continues to run indefinitely even after the component unmounts. This is because the returned cleanup function from `useEffect` is missing. This causes multiple interval timers to continue to run in the background.

## Solution
The solution involves returning a cleanup function from the `useEffect` hook. This function clears the interval when the component is unmounted.