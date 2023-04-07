# React-codeblocks
> Important code blocks
### Table of Contents

| No. | Questions |
| --- | --------- |
|1  | [Get Check if an Element is in the Viewport in React.js?](#Get-Check-if-an-Element-is-in-the-Viewport-in-React.js) |

### 1.Get Check if an Element is in the Viewport in React.js
```javascript
import {useEffect, useRef, useState, useMemo} from 'react';

export default function App() {
  const ref1 = useRef(null);
  const ref2 = useRef(null);

  const isInViewport1 = useIsInViewport(ref1);
  console.log('isInViewport1: ', isInViewport1);

  const isInViewport2 = useIsInViewport(ref2);
  console.log('isInViewport2: ', isInViewport2);

  return (
    <div>
      <div ref={ref1}>Top div {isInViewport1 && '| in viewport ✅'}</div>

      <div style={{height: '155rem'}} />

      <div ref={ref2}>Bottom div {isInViewport2 && '| in viewport ✅'}</div>
    </div>
  );
}

function useIsInViewport(ref) {
  const [isIntersecting, setIsIntersecting] = useState(false);

  const observer = useMemo(
    () =>
      new IntersectionObserver(([entry]) =>
        setIsIntersecting(entry.isIntersecting),
      ),
    [],
  );

  useEffect(() => {
    observer.observe(ref.current);

    return () => {
      observer.disconnect();
    };
  }, [ref, observer]);

  return isIntersecting;
}

```
### Why use the heigh ordered component in the react?
Higher-order components (HOCs) are a useful pattern in React for code reuse and component composition. HOCs are functions that take in a component and return a new component with some additional functionality or behavior.

There are several reasons why you might want to use HOCs in your React application:

Reusability: HOCs can be reused across different components and projects, reducing code duplication and improving maintainability.

Composition: HOCs can be composed together to create more complex components with multiple layers of functionality.

Separation of Concerns: HOCs can be used to separate concerns, such as logic for fetching data, authentication, or handling error messages, from the presentation layer of a component.

Code organization: HOCs can help organize your codebase by encapsulating functionality that can be applied to multiple components.

Code sharing: HOCs can be shared across teams or even open-sourced for other developers to use in their applications.

Overall, using HOCs can help make your codebase more modular, reusable, and maintainable, which can lead to faster development cycles and better code quality.

### how to use Suspense in react?
Suspense is a new feature introduced in React 16.6 that allows components to suspend rendering while they asynchronously fetch data. This can help improve the perceived performance of your application by reducing the amount of time users spend waiting for data to load.

Here's how you can use Suspense in React:

1. Wrap the component(s) that need to asynchronously fetch data in a Suspense component. The Suspense component should have a fallback prop that defines what to render while the component is waiting for data.
```javascript
import React, { Suspense } from 'react';

function MyComponent() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <AsyncComponent />
    </Suspense>
  );
}
```
2. Create an asynchronous component that returns a promise. This component will be loaded asynchronously and will not block the main thread.

const AsyncComponent = React.lazy(() => import('./AsyncComponent'));

3. In the AsyncComponent module, define the component that should be rendered after the data has been fetched.

```javascript
function AsyncComponent() {
  const data = fetchData(); // asynchronous data fetching
  return <div>{data}</div>;
}
```







**[⬆ Back to Top](#table-of-contents)**
