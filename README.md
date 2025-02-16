# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  Improperly using `setInterval` without a cleanup function leads to memory leaks, particularly when the component unmounts.

The `bug.js` file showcases the flawed code. The `bugSolution.js` file provides the corrected implementation.

**Problem:** The original `setInterval` call within the `useEffect` hook lacks a cleanup function to clear the interval when the component unmounts. This causes the interval to continue running indefinitely, leading to a memory leak.

**Solution:** The corrected version uses the return value of `useEffect` to execute a cleanup function. This function clears the interval when the component unmounts, preventing memory leaks.