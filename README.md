# React Memory Leak: setInterval without Cleanup

This repository demonstrates a common React memory leak caused by the improper use of `setInterval` within the `useEffect` hook.  The original `MyComponent` uses `setInterval` without a cleanup function, leading to a memory leak. The corrected version demonstrates how to properly clean up the interval.

## Problem

The `setInterval` function continues to run indefinitely, even if the component is unmounted.  This creates a memory leak because the interval keeps referencing the component's state and functions, preventing garbage collection.

## Solution

The solution involves using the return value of `useEffect` to implement a cleanup function. This cleanup function clears the interval when the component unmounts or when the dependency array changes.