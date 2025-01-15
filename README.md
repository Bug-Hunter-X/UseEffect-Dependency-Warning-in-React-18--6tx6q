# React 18 useEffect Dependency Warning

This repository demonstrates a common warning encountered when upgrading to React 18 or later: warnings related to missing dependencies in `useEffect` hooks.

The `bug.js` file contains the problematic code.  The `bugSolution.js` file shows the corrected code.

## Problem
In React 18 and later, React's `useEffect` hook has become stricter about its dependency array.  If you use a value from outside the dependency array *inside* your `useEffect`, you'll get warnings.  This can lead to unexpected behavior as the effect might not run when it should.

## Solution
Always include all values from the component's scope that your `useEffect` uses in the dependency array.  If you don't need the effect to run based on a value's changes, omit the value from the array.  If you intend for an effect to always run after render, add an empty array `[]` as your dependency array.