# Welcome to React Hooks


### 1. Use the use memo

Using memo will cause React to skip rendering a component if its props have not changed.This can improve performance.

```javascript
const Item = memo(({id, value, onChange}) => {
  return (
    <input
      onChange={e => onChange(id, e.target.value)}
      value={value} />
  )
})
```


### 2. Use the use useCallback
```javascript
const onChange = useCallback((id, value) => {
    setItems(prevItems => prevItems.map((item, index) => {
      return index !== id ? item : { value: value }
    }))
  }, []) 
```

 

#### useCallback Example
```javascript
const Parent = () => {
  ...

  const onChange = useCallback((id, value) => {
    setItems(items.map((item, index) => {
      return index !== id ? item : { value: value }
    }))
  }, [items])

  return (
    <div>
      {items.map((item, index) => (
        <Item
          key={index}
          id={index}
          value={item.value}
          onChange={onChange}
          />
      )}
    </div>
	)
}
```
### 3. useMemo hook

The React useMemo Hook returns a memoized value.
Think of memoization as caching a value so that it does not need to be recalculated.
The useMemo Hook only runs when one of its dependencies update.
This can improve performance.

**NOte:** ***The useMemo and useCallback Hooks are similar. The main difference is that useMemo returns a memoized value and useCallback returns a memoized function. You can learn more about useCallback in the useCallback chapter.***

Example:
```javascript
import "./styles.css";
import { useState, useMemo } from "react";
export default function App() {
  const [grade, setGrade] = useState(3);
  const countPopulation = (grade) => grade ** 2;
  const memoizedVal = useMemo(() => countPopulation(grade), [grade]);

  
  return (
    <div className="App">
      <RenderVal grade={grade} val={memoizedVal} />
    </div>
  );
}
const RenderVal = ({ grade, val }) => {
  return (
    <>
      <p>Current Grade: {grade}</p>
      <p>
        Current Population: {' '}
        {typeof val === 'function' ? val() : val}
      </p>
    </>
  );
```
### 4.UseCallback 

```javascript
import "./styles.css";
import { useState, useCallback  } from "react";
export default function App() {
  const [grade, setGrade] = useState(3);
  const countPopulation = countPopulation(grade), [grade]);
  const memoizedCallback = useCallback (() => countPopulation(grade), [grade]);

  return (
    <div className="App">
      <RenderVal grade={grade} val={memoizedCallback} />
    </div>
  );
}
const RenderVal = ({ grade, val }) => {
  return (
    <>
      <p>Current Grade: {grade}</p>
      <p>
        Current Population: {' '}
        {typeof val === 'function' ? val() : val}
      </p>
    </>
  );
};
```

### 5.Understanding of useImperativeHandle hook
[useImperativeHandle Hook Ultimate Guide](https://blog.webdevsimplified.com/2022-06/use-imperative-handle/)

The useImperativeHandle hook works in the similar phase of useRef hook but only it allows us to modify the instance that is going to be passed with the ref object which provides a reference to any DOM element. Although this hook is used in rare cases, it has some most advanced functionality.

**Syntax:**

useImperativeHandle(ref, createHandle, [deps])

Example:
input.js file
```javascript
import React, { useRef, useImperativeHandle, forwardRef } from 'react';
  
function Input(props, ref) {
  const btn = useRef();
  useImperativeHandle(ref, () => ({
    focus: () => {
      console.log('Input is in focus');
    },
  }));
  return <input ref={btn} {...props} placeholder="type here" />;
}
  
export default forwardRef(Input);
```
app.js file

```javascript
import React, { useRef } from 'react';
import Input from './Input';
const App = () => {
  const inputRef = useRef(null);
  return (
    <div>
      <Input onFocus={() => inputRef.current.focus()} 
      ref={inputRef} />
    </div>
  );
};
  
export default App;
```

### 6 useLayoutEffect

The useLayoutEffect works similarly to useEffect but rather working asynchronously like useEffect hook, it fires synchronously after all DOM loading is done loading. This is useful for synchronously re-rendering the DOM and also to read the layout from the DOM. But to prevent blocking the page loading, we should always use useEffect hook.

The useLayoutEffect hook works in the same phase as componentDidMount and componentDidUpdate methods. We should only use useLayoutEffect if useEffect isn’t outputting the expected result.

**Example**
useImperativeHandle(ref, createHandle, [deps])

```javascript
import React, { useLayoutEffect, useState } from 'react';
  
const App = () => {
  const [value, setValue] = useState('GFG');
    
  useLayoutEffect(() => {
    if (value === 'GFG') {
     // Changing the state 
      setValue('GeeksForGeeks');
    }
    console.log('UseLayoutEffect is called with the value of ', value);
  }, [value]);
  
  return <div>{value} is the greatest portal for geeks!</div>;
};
  
export default App;
```

### 7. disffrence between useEffect and useLayoutEffect
[useEffect vs useLayoutEffect](https://kentcdodds.com/blog/useeffect-vs-uselayouteffect)

### 8. ReactJs useDebugValue Hook
React useDebugValue Hook is introduced for the ReactJs versions above 18. React useDebugValue Hook helps developers to debug custom hooks.

**Example**
```javascript
import { useDebugValue, useState } from "react";
  
function useCount() {
    const [count, setCount] = useState(0);
  
    setInterval(() => {
        setCount(count + 1);
    }, 4000);
  
    useDebugValue(count);
    return count;
}
  
function App() {
    const count = useCount();
  
    return (
        <div className="App">
            <button>{count}</button>
        </div>
    );
}
  
export default App;
```
### 9.useDeferredValue hook

The useDeferredValue is a hook that will return a deferred version of the passed value. It takes in the state value and a timeout in milliseconds.
```javascript
import { useDeferredValue } from 'react';

const deferredValue = useDeferredValue(value, {
  timeoutMs: 5000
});
```
It is commonly used, to keep the UI responsive when we have something that renders immediately based on user input and something that needs to wait for a data fetch.

**Example**

```javascript
function App() {
  const [name, setName] = useState("")
  const deferredName = useDeferredValue(name)
  const list = useMemo(() => {
    return largeList.filter(item => item.name.includes(deferredName))
  }, [deferredName])

  function handleChange(e) {
    setName(e.target.value)
  }

  return <>
    <input type="text" value={name} onChange={handleChange} />
    {list.map(item => <ListComponent key={item.id} item={item} />)}
  </>
}
```

```javascript
import React, { useState, useDeferredValue } from "react";

const SearchPhotos = () => {
  const useStyles = makeStyles({
    container: {
      marginTop: '100px',
    }
  });
  const [title, setPhotoTitle] = useState("");
  const classes = useStyles();

  const onChange = (e) => {
    setPhotoTitle( e.target.value);React useId Hook is introduced for the ReactJS versions above 18. This hook generates unique IDs i.e, returns a string that is stable across both the server and the client sides.
  };
  const deferredValue = useDeferredValue(title, {
    timeoutMs: 5000
  });

  return (
    <Container className={classes.container}>
      <TextField id="standard-basic" label="Search by photo title" onChange={onChange} value={title}/>
      <PhotoCard searchParam={deferredValue}  isStale={deferredValue !== title} />
    </Container>
  );
};
```

[for more >>](https://github.com/reactwg/react-18/discussions/129)

### 10. useTransition Explained

The useTransition hook allows us to specify some state updates as not as important. These state updates will be executed in parallel with other state updates, but the rendering of the component will not wait for these less important state updates.

```javascript
function App() {
  const [name, setName] = useState("")
  const [list, setList] = useState(largeList)
  const [isPending, startTransition] = useTransition()

  function handleChange(e) {
    setName(e.target.value)
    startTransition(() => {
      setList(largeList.filter(item => item.name.includes(e.target.value)))
    })
  }

  return <>
    <input type="text" value={name} onChange={handleChange} />
    {isPending ? (
      <div>Loading...</div>
    ) : (
      list.map(item => <ListComponent key={item.id} item={item} />)
    )}
  </>
}
```
