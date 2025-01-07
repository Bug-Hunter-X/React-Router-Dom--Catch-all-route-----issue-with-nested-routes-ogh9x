# React Router Dom Catch-all Route Issue

This repository demonstrates a subtle bug in React Router Dom v6 related to the catch-all route ('*') when used in conjunction with nested routes.  The issue occurs when a catch-all route is defined at the top level, and this route unexpectedly overrides other correctly defined routes even when the URL perfectly matches a different route.

## Problem

The provided `App.js` demonstrates this problem.  Even when navigating to '/about', the 'Not Found' component is rendered because of the catch-all route. This is unexpected as the '/about' route should be matched first.

## Solution

The solution in `AppSolution.js` resolves the issue by using an order of routes such that the catch-all route only applies after all other routes are exhausted.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the unexpected behavior when navigating to '/about'.