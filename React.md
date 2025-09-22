# React

## Overview

React is a JavaScript library for building composable, reusable user interfaces. It focuses on rendering UI as a function of state, making it simple to reason about complex, data-driven views that change over time.

## Why React?

- Component-based: Build UIs by composing small, reusable components.
- Declarative: Describe what the UI should look like; React updates the DOM for you.
- One-way data flow: Predictable updates that are easier to debug and test.
- JSX (optional): An HTML-like syntax in JavaScript that improves readability.

## How React Works

- No templates: Instead of HTML templates or directives, React uses JavaScript to describe UI.
- Virtual DOM: Components render to a lightweight description of the DOM. On updates, React diffs this description and applies the minimal changes to the real DOM.
- Reconciliation: The process of comparing previous and next render outputs to efficiently update the UI.

## econciliation in Depth

When a component first initializes, its render function produces a lightweight description of the UI. From this description, markup is generated and inserted into the document. When state or props change, render runs again. React diffs the new description against the previous one and applies only the minimal set of DOM changes needed.

The value returned from render is not a string or a DOM node. It is a declarative description of what the UI should look like. React’s diffing and update process is called reconciliation.

Because the re-render and diff are very fast (e.g., on the order of milliseconds for simple apps like TodoMVC), developers don’t need to write imperative data bindings or manual DOM updates. This keeps components simple and predictable.

## Key Benefits

- Maintainability: Co-locate markup with logic, making components easier to extend and maintain.
- Safety: Less manual string concatenation reduces XSS surface area.
- Performance: Fast re-renders enable simple, declarative data bindings without manual DOM updates.

## Common Use Cases

- Dynamic dashboards and data-heavy apps.
- Single Page Applications (SPAs) with client-side routing.
- Server-rendered apps for SEO and performance.

## Ecosystem and Platform Reach

- Web: Standard React components render to the DOM.
- Canvas and beyond: UIs can render to targets like <canvas> when needed.
- Mobile and native: Concepts power native experiences via bridges (e.g., iOS views via Objective-C bridges).
- Workers and servers: Can run in web workers and on servers for performance and flexibility.

## Platform Examples

- Facebook uses dynamic charts that render to <canvas> instead of HTML.
- Instagram is a single-page app built with React and Backbone.Router; designers contribute React code with JSX.
- Internal prototypes have run React apps inside web workers and driven native iOS views via an Objective-C bridge.
- Server rendering enables SEO, performance wins, and code sharing.

Consistent Events

React normalizes events to behave consistently across browsers and uses efficient event delegation under the hood.

Example

```jsx
import { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);
  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  );
}
```

## Notes and Case Study Highlights

- Facebook engineers created React to simplify building large, dynamic UIs where data changes frequently.
- Compared with traditional MVC frameworks, React concentrates on the View layer with a component model and declarative updates.
- Even in frameworks that offer data binding, developers often need manual DOM hooks; React replaces this with diffing and reconciliation.
- Real-world examples include Instagram’s single-page app and Facebook’s dynamic visualizations.

#Learn More

- Official site: https://reactjs.org
- Concepts: Components, JSX, Props, State, Effects, Context, Refs, Keys