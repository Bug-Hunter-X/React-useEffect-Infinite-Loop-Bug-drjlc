# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by incorrectly managing dependencies.  The `useEffect` hook, while powerful, requires careful consideration of its dependency array to prevent unintended side effects.  This example shows how a missing dependency or an incorrect update can lead to performance issues and crashes.

## Problem
The `MyComponent` function uses `useEffect` to update the `count` state.  However, the dependency array is empty (`[]`), causing the effect to run after every render, resulting in an infinite loop.

## Solution
The solution involves correctly specifying dependencies in the `useEffect`'s dependency array.  If you want to update `count` only once after the component mounts, you leave the array empty.  If you need to trigger the effect based on changes to other variables, then include them in the dependency array.