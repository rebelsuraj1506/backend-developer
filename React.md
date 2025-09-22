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

## Reconciliation in Depth

When a component first initializes, its render function produces a lightweight description of the UI. From this description, markup is generated and inserted into the document. When state or props change, render runs again. React diffs the new description against the previous one and applies only the minimal set of DOM changes needed.

The value returned from render is not a string or a DOM node. It is a declarative description of what the UI should look like. React’s diffing and update process is called reconciliation.

Because the re-render and diff are very fast (e.g., on the order of milliseconds for simple apps like TodoMVC), developers don’t need to write imperative data bindings or manual DOM updates. This keeps components simple and predictable.

## The Virtual DOM

React builds a representation of the browser Document Object Model or DOM in memory called the virtual DOM. As components are updated, React checks to see if the component’s HTML code in the virtual DOM matches the browser DOM. If a change is required, the browser DOM is updated. If nothing has changed, then no update is performed.

As you know, this is called the reconciliation process and can be broken down into the following steps:

Step 1: The virtual DOM is updated.

Step 2: The virtual DOM is compared to the previous version of the virtual DOM and checks which elements have changed.

Step 3: The changed elements are updated in the browser DOM.

Step 4: The displayed webpage updates to match the browser DOM.

As updating the browser DOM can be a slow operation, this process helps to reduce the number of updates to the browser DOM by only updating when it is necessary.

But even with this process, if a lot of elements are updated by an event, pushing the update to the browser DOM can still be expensive and cause slow performance in the web application.

## React Fiber Architecture

The React team invested many years of research into solving this problem. The outcome of that research is what’s known as the React Fiber Architecture.

The Fiber Architecture allows React to incrementally render the web page. What this means is that instead of immediately updating the browser DOM with all virtual DOM changes, React can spread the update over time. But what does "over time" mean?

Imagine a really long web page in the web browser. If the user scrolls to the bottom, the top of the web page is no longer visible. The user then clicks a button on the bottom of the web page that updates some text on the top of the web page.

But the top of the page isn’t visible. Therefore, why update it immediately?

Perhaps there is text currently displayed on the bottom of the page that also updates when the button is clicked. Wouldn’t that be a higher priority to update than the non-visible text?

This is the principle of the React Fiber Architecture. React can optimize when and where updates occur to the browser DOM to significantly improve application performance and responsiveness to user input. Think of it as a priority system. The highest priority changes, the elements visible to the user, are updated first. While lower priority changes, the elements not currently displayed, are updated later.

While you’re unlikely to interact with the virtual DOM and Fiber Architecture yourself, it’s good to know what’s going on if issues occur during the development of your web application.

## Tools for Insight

There are many tools available to help you investigate how React is processing your webpage. The official React Developer Tools web browser plugin developed by Meta will be one of the key tools in your developer toolbox. So, if you do have to look deeper into the code, you’ll have the right toolbox available to help you. These tools will be explored later on.

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

# React and complimentary libraries

React is a library and not a framework. This means you'll often use other JavaScript libraries with it to build your application. In this reading, you will be briefly introduced to some JavaScript libraries commonly used with React.

## Lodash

Official Website : [Lodash](https://lodash.com/)

As a developer, there's a lot of logic you'll commonly write across applications. For example, you might need to sort a list of items or round a number such as 3.14 to 3. Lodash provides common logic such as these as a utility library to save you time as a developer.

Other Javascript libraries: Lodash

## Luxon

Official Website : [Luxon](https://moment.github.io/luxon/#/)

You'll be working with dates and times often as a developer. Think of viewing a list of orders and when they were placed, or displaying a calendar schedule for an event. Dates and times are everywhere.

Luxon helps you work with dates and times by providing functions to manipulate and display them. For example, think of how dates are formatted in different countries. In the United States the format is Month Day Year but in Europe it is Day Month Year. This is one area where Luxon can help you display the date in the user's local format.

Other Javascript libraries: Luxon

## Redux

Official Website : [Redux](https://redux.js.org/)

When building a web application, you'll need to keep track of its state. Think of when you shop online. The web application tracks items currently in your shopping cart. When you remove an item from the cart, the application needs to update what displays on the screen. This is where Redux comes in. It helps you manage your application state and even has advanced features such as undo and redo.

Other Javascript libraries: Redux

## Axios

Official Website : [Axios](https://axios-http.com/)

As a developer you'll be communicating with APIs over HTTP frequently. The Axios library helps to simplify sending HTTP requests and processing the response. It also provides advanced features allowing you to cancel requests and to change data received from the web server before your application uses the data.

Other Javascript libraries: Axios 

## Jest

Official Website : [Jest](https://jestjs.io/)

It is good practice to write automated tests for your code as a professional developer. The jest library helps you to do this and works with many libraries and frameworks. It also provides reporting utilities such as providing information on how much of your code is tested by your automated tests.

Other Javascript libraries: Jest 

## Conclusion

If you're curious to learn more about these libraries, their websites feature setup guides, tutorials and documentation to get started. These libraries will be covered later on.

# Learn More

- Official site: https://reactjs.org
- Concepts: Components, JSX, Props, State, Effects, Context, Refs, Keys