# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications where an infinite loop occurs within the `useEffect` hook.  The issue stems from improperly managing the dependency array, leading to continuous re-renders and performance problems.

## Bug Description
The provided `MyComponent` utilizes the `useEffect` hook to increment a state variable (`count`) on every render. The dependency array `[count]` causes the effect to run whenever `count` changes, but because `setCount` updates `count`,  this creates an endless loop of updates. 

## Solution
The solution modifies the `useEffect` hook to only run when the component initially mounts. By removing the dependency array, the effect executes only once after the initial render.