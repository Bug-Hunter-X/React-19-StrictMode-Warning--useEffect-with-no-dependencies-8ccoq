# React 19 StrictMode Warning: useEffect with no dependencies

This repository demonstrates a common warning encountered when using `useEffect` hooks in React 19's StrictMode.  The warning arises when `useEffect` is called without specifying any dependencies, causing it to execute on every render, potentially leading to unnecessary computations and performance issues.

## Problem

The provided `bug.js` file contains a `MyComponent` that utilizes `useEffect` without a dependency array.  This results in the following warning message in the browser's console when StrictMode is enabled:

> Warning: An effect is creating a state change inside the component. This is likely a mistake. Use `React.useCallback` to handle state changes more efficiently.

This warning suggests the component is modifying its state within the effect, triggering a re-render and creating an infinite loop of updates and warnings.

## Solution

The `bugSolution.js` file fixes the issue by providing an empty dependency array `[]` to the `useEffect` hook. This ensures the effect runs only once after the initial mount, preventing the unnecessary re-renders and warnings.