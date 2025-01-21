# React setInterval in useEffect without cleanup
This repository demonstrates a common React bug involving the improper use of `setInterval` within the `useEffect` hook without a cleanup function.  This leads to memory leaks and unexpected behavior.

The `bug.js` file showcases the problematic code. The `bugSolution.js` file provides the corrected implementation.

## Bug Description
The original code uses `setInterval` to update a counter every second.  However, it fails to clear the interval when the component unmounts, leading to continued updates even after the component is no longer rendered, thus causing memory leaks.

## Solution
The solution involves using the return value of `useEffect` to clear the interval when the component unmounts. This ensures that the interval is properly stopped, preventing resource leaks and ensuring correct behavior.