# React useEffect Hook Memory Leak

This repository demonstrates a common bug in React applications involving the `useEffect` hook: memory leaks due to missing cleanup functions.

## The Bug

The `bug.js` file contains a component that uses `useEffect` to set up an interval.  However, it fails to include a cleanup function to clear the interval when the component unmounts. This leads to the interval continuing to run indefinitely, even after the component is removed from the DOM. This is a memory leak.

## The Solution

The `bugSolution.js` file provides a corrected version of the component, including a cleanup function to clear the interval using `clearInterval` before the component unmounts. This prevents the memory leak.

## How to reproduce
1. Clone this repo
2. run `npm install`
3. run `npm start`
4. Open the app in browser
5. observe the counter in the browser
6. navigate away from the app and check the browser's console for errors or warnings.  With the bug, the interval will still continue to run
7. Now modify the code in `bugSolution.js` to the code in `bug.js` then repeat steps 4-6
