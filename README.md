# React setInterval Memory Leak

This repository demonstrates a common error in React: using `setInterval` within `useEffect` without proper cleanup. This leads to memory leaks as the interval continues even after the component unmounts.

## Bug

The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it lacks the cleanup function required by `useEffect` to stop the interval when the component unmounts.

## Solution

The `bugSolution.js` file provides a corrected version with a cleanup function that uses `clearInterval` to stop the interval before the component unmounts, thus preventing the memory leak.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter in the browser. Unmounting the component and remounting will show that the interval continues in the original code.