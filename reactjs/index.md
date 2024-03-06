## Table of Contents

- [Basics](#basics)
- [Props and State](#props-and-state)
- [Refs](#refs)
- [Optimization](#optimization)
- [Virtual DOM](#virtual-dom)
- [Redux](#redux)
- [Typescript](#typescript)
- [Styling](#styling)
- [React Router](#react-router)
- [React DOM](#react-dom)
- [Events](#events)
- [Hooks](#hooks)
- [Diff](#diff)

## Basics

**What is React?**

- React is a JavaScript library for building user interfaces. It allows developers to create reusable UI components and manage the dynamic rendering of web pages efficiently.

**What are the major features of React?**

- Key features of React include a component-based architecture, virtual DOM for efficient updates, JSX for declarative UI, and a strong community with a rich ecosystem.

**What is JSX?**

- JSX (JavaScript XML) is a syntax extension for JavaScript used in React to describe the structure and content of user interfaces. It allows you to write HTML-like code in JavaScript files.

**Is it possible to use React without JSX?**

- Yes, it is possible to use React without JSX. JSX is a syntax extension for JavaScript that allows you to write HTML-like code in your JavaScript files, but it is not required to use React.

- Instead of using JSX, you can use plain JavaScript to create React elements. For example, you can use the React.createElement() method to create a new element:

  ```javascript
  const element = React.createElement(
    'h1',
    { className: 'greeting' },
    'Hello, world!'
  );
  ```

- This creates a new `h1` element with a `className` of 'greeting' and a text content of 'Hello, world!'.

**What is the difference between Element and Component?**

- An element is a plain JavaScript object that describes a component's UI at a specific point in time.

- A component is a reusable, self-contained piece of UI that can contain multiple elements.

**What is the difference between `createElement` and `cloneElement`?**

- `createElement` is what JSX gets transpiled to and is what React uses to create React Elements (object representations of some UI). `cloneElement` is used in order to clone an element and pass it new props.

**How to create components in React?**

- Components in React can be created as either functional components (using functions) or class components (using ES6 classes).

**How to bind methods or event handlers in JSX callbacks?**

- You can bind methods in class components using the `.bind()` method in the constructor or by using arrow functions.

**How to pass a parameter to an event handler or callback?**

- You can pass parameters to event handlers by using arrow functions in JSX or by binding the parameters when calling the event handler.

## Props and State

**What is state in React?**

- State in React is a JavaScript object used to store data that affects a component's behavior and rendering.

**What are props in React?**

- Props are inputs to components. They are single values or objects containing a set of values that are passed to components on creation using a naming convention similar to HTML-tag attributes. They are data passed down from a parent component to a child component.
- The primary purpose of props in React is to provide following component functionality:
  1. Pass custom data to your component.
  2. Trigger state changes.

**Why we need to be careful when spreading props on DOM elements?**

- When we spread props we run into the risk of adding unknown HTML attributes, which is a bad practice. Instead we can use prop destructuring with `...rest` operator, so it will add only required props.

**What is `children` prop?**

- `children` is a prop (`this.props.children`) that allows you to pass components as data to other components, just like any other prop you use. Component tree put between component's opening and closing tag will be passed to that component as children prop.
- There are several methods available in the React API to work with this prop. These include `React.Children.map`, `React.Children.forEach`, `React.Children.count`, `React.Children.only`, `React.Children.toArray`.

**What is the `key` prop, and what is the benefit of using it in arrays of elements?**

- The `key` prop is a unique identifier for elements in a list. It helps React identify which items have changed, been added, or been removed when rendering arrays of elements, improving performance and preventing unexpected behavior.

**What are render props?**

- Render Props is a simple technique for sharing code between components using a prop whose value is a function. The below component uses render prop which returns a React element.
  ```javascript
  <DataProviderrender = {data => (<h1>{`Hello ${data.target}`}</h1>)}/>
  ```
- Libraries such as React Router and DownShift are using this pattern.

**Can child component change the props passed from parent component?**

- No. Whether it is a class component or function component, props can never be updated in the child component.

**Why we pass props as an argument in `super`?**

- A child class constructor cannot make use of this reference until the `super()` method has been called. The same applies to ES6 sub-classes as well. The main reason for passing props parameter to `super()` call is to access `this.props` in your child constructors.

**What is the difference between state and props?**

- State is mutable and managed within a component, while props are immutable and passed to a component from its parent.

- State is used for internal component data, and props are used for communication between components.

**Why should we not update the state directly?**

- Directly updating the state can lead to unpredictable behavior. React's state updates should be done using `setState()` or `useState()` to ensure proper rendering and component lifecycle management.

**Is the state updated synchronously?**

- No, state updates in React are asynchronous. For example, when you call `setState()`, React batches state updates for performance reasons and may batch multiple updates together.

## Refs

**What is the use of refs?**

- Refs in React are used to access the DOM directly or to interact with child components imperatively. They are often used for managing focus, triggering animations, or accessing specific elements.

**How to create refs?**

- Refs can be created using the `React.createRef()` API in class components or using the `useRef` hook in functional components.

## Optimization

**How to prevent child component from re-rendering?**

- We can use the `shouldComponentUpdate` method or can use pure components in the case of class components. In functional components, we can make use of `React.memo` hook.

**What would be the common mistake of function being called every time the component renders?**

- You need to make sure that function is not being called while passing the function as a parameter.

  ```javascript
  render() {
    // Wrong: handleClick is called instead of passed as a reference!
    return <button onClick={this.handleClick()}>{'Click Me'}</button>
  }
  ```

**What is `React.memo` function?**

- Class components can be restricted from re-rendering when their input props are the same using `PureComponent` or `shouldComponentUpdate`. Now you can do the same with function components by wrapping them in `React.memo`.

**`React.memo` VS `useMemo`**

- `React.memo` is a higher-order component used for memoizing functional components to prevent unnecessary re-renders.

- `useMemo` is a hook used for memoizing values in functional components to avoid redundant calculations.

**How do you memoize a component?**

- You can memoize a functional component using `React.memo` by wrapping the component with it.

## Virtual DOM

**What is Virtual DOM?**

- The Virtual DOM is a lightweight in-memory representation of the actual DOM. It is used in React to optimize rendering by reducing direct manipulation of the real DOM.

**How does Virtual DOM work?**

- The Virtual DOM works by creating a tree of JavaScript objects that represent the structure of the actual DOM. Each object in the tree represents a DOM element, and contains information about its type, attributes, and children. When a component's state changes, React creates a new Virtual DOM tree that reflects the new state of the component.

- React then compares the new Virtual DOM tree to the previous Virtual DOM tree, and identifies the minimum number of changes needed to update the actual DOM to match the new Virtual DOM tree. This process is called "reconciliation".

- Once React has identified the changes that need to be made to the actual DOM, it updates the DOM in a batched process, minimizing the number of actual DOM manipulations that need to be performed.

- The Virtual DOM allows React to update the UI in an efficient and performant way, without requiring developers to manually manipulate the actual DOM. By minimizing the number of actual DOM manipulations, React can provide a smoother and more responsive user experience, especially for complex and dynamic UIs.

**What is the difference between Shadow DOM and Virtual DOM?**

- Shadow DOM is a web standard for encapsulating and styling components, often used in web components.

- Virtual DOM is a concept specific to React for optimizing DOM updates by using a lightweight in-memory representation.

**What is React Fiber?**

- React Fiber is a reimplementation of React's core algorithm, designed to improve performance and allow for incremental updates and more granular control over rendering.

**What is the main goal of React Fiber?**

- The main goal of React Fiber is to enable smoother animations, improved performance, and better handling of asynchronous rendering in React applications.

**What are the different phases of component lifecycle?**

- The component lifecycle in React includes three main phases:
  - mounting;
  - updating;
  - unmounting.

**What are the lifecycle methods of React?**

- Lifecycle methods in React include `componentDidMount`, `componentDidUpdate`, `componentWillUnmount`, and others. However, many of them are deprecated in recent versions in favor of hooks.

**What are Higher-Order components?**

- Higher-Order components (HOCs) are functions that take a component and return a new component with added functionality. They are used for code reuse and logic sharing.

**How to fetch data with React Hooks?**

- Data fetching in React can be done using the `useEffect` hook in combination with functions like `fetch`, `axios`, or other AJAX libraries.

**What is context?**

- Context in React is an API for sharing state between components without having to pass props manually through multiple levels of the component tree.

**What is `children` prop?**

- The `children` prop is a special prop in React that allows you to pass components or elements as children to a parent component. It is often used for creating reusable and flexible components.

**What is reconciliation?**

- Reconciliation is the process by which React updates the DOM to match the most recent state of the Virtual DOM. It ensures that the actual DOM reflects the desired UI.

**How do you conditionally render components?**

- In React, you can conditionally render components by using JavaScript expressions inside JSX. You can use any JavaScript expression, including `if` statements and ternary operators, to determine whether a component should be rendered or not.

**What are error boundaries in React v16?**

- Error boundaries are special components introduced in React v16 that allow you to catch and handle errors that occur during rendering in components below them in the tree.

**What are hooks? React hooks rules**

- Hooks are functions that allow functional components to "hook into" React state and lifecycle features. Rules for hooks include using them at the top level and not inside loops or conditions.

**What is Lifting State Up in React?**

- Lifting State Up is a pattern in React where you move the shared state of multiple components to a common ancestor component to manage it centrally and pass it down as props.

**What are fragments? Why are fragments better than container divs?**

- Fragments are a way to group multiple elements in React without introducing unnecessary container divs to the DOM. They improve code readability and reduce DOM clutter.

## Redux

**What is Flux?**

- Flux is an architectural pattern used for managing data flow in React applications. It enforces unidirectional data flow and helps manage complex state.

**What is Redux?**

- Redux is a predictable state container for JavaScript apps, most commonly used with React. It provides a centralized store for managing the state of your application, and provides a set of rules and patterns for updating that state in a predictable way.

- The core concept of Redux is that the state of your application is stored in a single object called the "store". The store is responsible for managing the state of your application, and provides methods for updating that state in a predictable way. The state of the store can only be modified by dispatching "actions", which are plain JavaScript objects that describe the changes that should be made to the state.

- When an action is dispatched, it is passed to a "reducer", which is a pure function that takes the current state of the store and the action, and returns a new state. The reducer is responsible for updating the state of the store in response to the action.

- Redux also provides a set of middleware that can be used to extend the functionality of the store. Middleware can be used for things like logging, asynchronous actions, and more.

**What hooks does Redux have?**

- Redux provides hooks like `useSelector` and `useDispatch` for interacting with the Redux store in functional components.

**What are the core principles of Redux?**

- The core principles of Redux include a single source of truth (the store), state is read-only, changes are made with pure functions (reducers), and predictable state updates.

**What are the downsides of Redux compared to Flux?**

- Redux can introduce more boilerplate code than Flux, and it may have a steeper learning curve. However, it offers more predictable and scalable state management.

**Can I dispatch an action in a reducer?**

- No, you should not dispatch actions from reducers in Redux. Reducers should be pure functions responsible for updating the state based on actions dispatched by other parts of the application.

**How to access Redux store outside a component?**

- To access the Redux store outside a component, you can use the `store.getState()` method provided by Redux.

**What is the difference between React context and React Redux?**

- React context is a built-in React feature for passing state between components, while React Redux is a third-party library specifically designed for managing application state.

**Should I keep all component's state in the Redux store?**

- No, not all component state should be stored in Redux. Use Redux for global or shared state and local component state for isolated and non-shared data.

**What is the proper way to access the Redux store?**

- The proper way to access the Redux store is by using the `useSelector` hook or the `connect` function provided by React Redux.

**What is an action in Redux?**

- An action in Redux is a plain JavaScript object that describes an event or change in the application's state. It must have a `type` property and may contain additional payload.

**What is the purpose of the constants in Redux?**

- Constants in Redux are used to define unique action types, ensuring that action types are consistent and not prone to typos or duplication.

## Typescript

**How do you create a functional component in React with TypeScript?**

- You can create a functional component by defining a function that returns JSX. For example:

  ```javascript
  const MyComponent: React.FC = () => {
    return <div>Hello, React!</div>;
  };
  ```

**How can you handle form input in React with TypeScript, and how do you type input event handlers?**

- You can use controlled components for form inputs. Type input event handlers with `React.ChangeEvent<HTMLInputElement>`.

**Explain the useState hook in React and how you can define its type with TypeScript.**

- `useState` allows functional components to manage state. You can define its type using TypeScript generics, such as `useState<number>(0)`.

**Explain how to work with external libraries and non-TypeScript code in a React TypeScript project.**

- You can create declaration files (.d.ts) or use type assertion to add types to external libraries and non-TypeScript code.

**How can you define prop types with default values in React TypeScript components?**

- You can set default values for props using the defaultProps property on a functional component or static defaultProps in a class component.

**What is React's synthetic event system, and how do you type event objects in TypeScript?**

- React's synthetic events provide a cross-browser interface for handling events. TypeScript defines event types, such as `React.MouseEvent`.

**What are the advantages of using TypeScript with React over regular JavaScript?**

- TypeScript provides type safety, better tooling, improved documentation, and enhanced code quality, making it an excellent choice for React development.

**Explain the role of the `key` prop in React, and how can you type it with TypeScript?**

- The `key` prop helps React identify elements in lists. You can type it using TypeScript as `key?: React.Key`.

**What are the benefits of using TypeScript's strict mode in a React project, and how do you enable it?**

- TypeScript's strict mode helps catch more type-related errors. You can enable it by configuring the tsconfig.json file.

**How can you use TypeScript's "strictNullChecks" option to improve code quality in a React TypeScript project?**

- Enabling "strictNullChecks" ensures that variables are not accessed before checking for null or undefined, reducing potential runtime errors.

## Styling

**What are Styled Components?**

- styled-components is a JavaScript library for styling React applications. It removes the mapping between styles and components, and lets you write actual CSS augmented with JavaScript.

**Give an example of Styled Components**

- Lets create `<Title>` and `<Wrapper>` components with specific styles for each.

  ```javascript
  const Title = styled.h1`
    font-size: 1.5em;
    text-align: center;
    color: palevioletred;
  `;
  const Wrapper = styled.section`
    padding: 4em;
    background: papayawhip;
  `;
  ```

- These two variables, `Title` and `Wrapper`, are now components that you can render just like any other react component.

  ```javascript
  <Wrapper>
    <Title>{'Lets start first styled component!'}</Title>
  </Wrapper>
  ```

**Is it recommended to use CSS In JS technique in React?**

- React does not have any opinion about how styles are defined but if you are a beginner then good starting point is to define your styles in a separate \*.css file as usual and refer to them using className. This functionality is not part of React but came from third-party libraries. But If you want to try a different approach (CSS-In-JS) then styled-components library is a good option.

## React Router

**What is React Router?**

- React Router is a powerful routing library built on top of React that helps you add new screens and flows to your application incredibly quickly, all while keeping the URL in sync with what's being displayed on the page.
- It provides hooks like `useHistory`, `useLocation`, and `useParams` for managing routing-related functionality.

**How React Router is different from history library?**

- React Router is a wrapper around the history library which handles interaction with the browser's `window.history` with its browser and hash histories. It also provides memory history which is useful for environments that don't have global history, such as mobile app development (React Native) and unit testing with Node.

## React DOM

**What is the use of react-dom package?**

- The react-dom package provides DOM-specific methods that can be used at the top level of your app. Most of the components are not required to use this module. Some of the methods of this package are:
  1. render()
  2. hydrate()
  3. unmountComponentAtNode()
  4. findDOMNode()
  5. createPortal()

**What is the difference between React and ReactDOM?**

- The `react` package contains `React.createElement()`, `React.Component`, `React.Children`, and other helpers related to elements and component classes. You can think of these as the isomorphic or universal helpers that you need to build components. The `react-dom` package contains `ReactDOM.render()`, and in `react-dom/server` we have server-side rendering support with `ReactDOMServer.renderToString()` and `ReactDOMServer.renderToStaticMarkup()`.

**Why ReactDOM is separated from React?**

- The React team worked on extracting all DOM-related features into a separate library called ReactDOM. React v0.14 is the first release in which the libraries are split. By looking at some of the packages, `react-native`, `react-art`, `react-canvas`, and `react-three`, it has become clear that the beauty and essence of React has nothing to do with browsers or the DOM.
  To build more environments that React can render to, React team planned to split the main React package into two: react and react-dom. This paves the way to writing components that can be shared between the web version of React and React Native.

**What is the purpose of `render` method of react-dom?**

- This method is used to render a React element into the DOM in the supplied container and return a reference to the component. If the React element was previously rendered into container, it will perform an update on it and only mutate the DOM as necessary to reflect the latest changes.

## Events

**How events are different in React?**

- Handling events in React elements has some syntactic differences:
  1. React event handlers are named using camelCase, rather than lowercase.
  2. With JSX you pass a function as the event handler, rather than a string.

**What are synthetic events?**

- SyntheticEvent is a cross-browser wrapper around the browser's native event. Its API is same as the browser's native event, including `stopPropagation()` and `preventDefault()`, except the events work identically across all browsers.

**How do you pass an event handler to a component?**

- You can pass event handlers and other functions as props to child components. It can be used in child component as below.

  ```javascript
  <button onClick={this.handleClick}>
  ```

**How to programmatically trigger click event in React?**

- You could use the `ref` prop to acquire a reference to the underlying HTMLInputElement object through a callback, store the reference as a class property, then use that reference to later trigger a click from your event handlers using the HTMLElement.click method.
- This can be done in two steps:
  1. Create `ref` in render method:
  ```javascript
  <input ref={(input) => (this.inputElement = input)} />
  ```
  2. Apply `click` event in your event handler:
  ```javascript
  this.inputElement.click();
  ```
  **What are the Pointer Events supported in React?**
- Pointer Events provide a unified way of handling all input events. In the old days we had a mouse and respective event listeners to handle them but nowadays we have many devices which don't correlate to having a mouse, like phones with touch surface or pens. We need to remember that these events will only work in browsers that support the Pointer Events specification.
- The following event types are now available in React DOM:
  1. onPointerDown
  2. onPointerMove
  3. onPointerUp
  4. onPointerCancel
  5. onGotPointerCapture
  6. onLostPointerCapture
  7. onPointerEnter
  8. onPointerLeave
  9. onPointerOver
  10. onPointerOut

**How to bind methods or event handlers in JSX callbacks?**

- There are 3 possible ways to achieve this:
  1.  Binding in Constructor: In JavaScript classes, the methods are not bound by default. The same thing applies for React event handlers defined as class methods. Normally we bind them in constructor.
  2.  Public class fields syntax: If you don't like to use bind approach then public class fields syntax can be used to correctly bind callbacks.
  3.  Arrow functions in callbacks: You can use arrow functions directly in the callbacks.
- _Note:_ If the callback is passed as prop to child components, those components might do an extra re-rendering. In those cases, it is preferred to go with `.bind()` or public class fields syntax approach considering performance.

## Hooks
**What is the purpose of the `useLayoutEffect` hook?**
- `useLayoutEffect` is similar to `useEffect`, but it fires synchronously after all DOM mutations. It is often used for measuring and synchronizing layout.

**What is the purpose of the `useImperativeHandle` hook?**
- React supports code splitting, allowing developers to split their code into smaller chunks that are loaded on demand, improving performance by reducing the initial bundle size.

**Explain the concept of the `useDebugValue` hook.**
- `useDebugValue` is used to display a label for custom hooks in React DevTools.

## Diff

**What is strict mode in React?**

- `React.StrictMode` is a useful component for highlighting potential problems in an application. Just like `<Fragment>`, `<StrictMode>` does not render any extra DOM elements. It activates additional checks and warnings for its descendants. These checks apply for development mode only.

**Why do we use arrow functions in React and what problem do they solve?**

- The `this` keyword works differently in arrow functions. They do not bind their own `this`, instead, they inherit one from the parent scope, which is called “lexical scoping”. If we didn’t use arrow functions, we would need to bind `this` to the parent, which is normally done in the constructor.

**What are keys in React and why do we need them?**

- In short, keys are used in React for diffing algorithm. With the help of keys React can tell which DOM node was changed and update only that one. They are essential when mapping over arrays.
