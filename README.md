# React Native FlatList Performance Optimization

This repository demonstrates a common performance issue in React Native's `FlatList` component when dealing with large datasets and complex list items.  The `bug.js` file showcases the problem, while `bugSolution.js` offers optimized solutions.

## Problem

Using `FlatList` with a large dataset and computationally expensive render items leads to significant performance degradation.  Symptoms include:

* Slow initial rendering
* Janky scrolling
* Frequent re-renders
* Potential app crashes due to memory issues

## Solution

The solution involves several optimization strategies:

1. **Efficient `keyExtractor`:** Ensure a unique and stable key for each item to minimize unnecessary re-renders.
2. **Memory Optimization:** Avoid creating and destroying components unnecessarily.  Use techniques like `React.memo` and `useMemo` to prevent repeated computations.
3. **Component Optimization:** Simplify and optimize the rendering logic of `renderItem`.  Use `React.memo` on complex components to prevent unnecessary re-renders.
4. **Virtualization:** Consider using `windowSize` to limit the number of rendered items at any given time.
5. **Data Management:**  Pre-process your data if possible to minimize calculations within the `renderItem` function.

## Setup

1. Clone the repository.
2. Navigate to the project directory.
3. Run `npm install`.
4. Run `npx react-native run-android` or `npx react-native run-ios`.

## Note:
The provided code snippets and solutions are illustrative and might require adjustments depending on the specific complexity of your data and components.  Consider using profiling tools to further identify performance bottlenecks.