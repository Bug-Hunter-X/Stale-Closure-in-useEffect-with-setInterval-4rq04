# Stale Closure in React's useEffect Hook

This repository demonstrates a common error in React applications when using the `useEffect` hook with `setInterval`.  The problem arises from the closure created within the `setInterval` callback, leading to stale data.

## The Problem

The `bug.js` file contains a component that uses `setInterval` to increment a counter every second.  However, the `count` variable used within `setInterval` is a closure, always referencing the latest value of `count` after the effect has run. This results in the counter jumping erratically instead of incrementing smoothly. 

## The Solution

`bugSolution.js` provides a corrected implementation. The key is to ensure that the state variable's value is updated correctly within the callback using functional updates.

## How to reproduce

1. Clone this repo.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter in the browser.