# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug causes an infinite render loop due to an incorrect state update within the effect's callback.

## Bug Description

A React component uses the `useEffect` hook to update a state variable. However, the update is performed in a way that triggers a re-render, leading to an infinite loop.  This happens because the update within the `useEffect` depends directly on the current state, triggering a new render immediately after the update, creating a continuous cycle.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console for error messages and the browser for the effect of the infinite render loop.

## Solution

The provided `bugSolution.js` demonstrates the corrected code. The key fix is to avoid directly using the current state value within the useEffect callback when the callback is only intended to run once upon mount.