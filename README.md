# Uncontrolled setInterval in useEffect causing memory leak

This example demonstrates a common mistake in React: using `setInterval` within the `useEffect` hook without proper cleanup. This leads to memory leaks and unexpected behavior.

## Problem

The `setInterval` function continuously updates the `count` state every second.  However, because there's no cleanup function in the `useEffect`, the interval continues even after the component unmounts, leading to memory leaks.

## Solution

The solution involves returning a cleanup function from `useEffect` that clears the interval when the component unmounts or when the dependencies change.