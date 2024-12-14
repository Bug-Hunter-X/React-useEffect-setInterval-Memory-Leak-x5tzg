# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  The example shows a memory leak caused by not properly cleaning up the interval when the component unmounts.

## Bug Description:
The `MyComponent` uses `setInterval` within a `useEffect` hook to update a counter every second. However, it fails to include a cleanup function to `clearInterval` when the component is unmounted. This leads to the interval continuing to run indefinitely, even after the component is removed from the DOM. This causes a memory leak and can negatively impact the performance of the application.

## Solution:
The solution demonstrates how to properly clean up the interval using a return function from `useEffect`. This function is executed when the component unmounts or when the dependencies change, ensuring that `setInterval` is stopped, preventing memory leaks.