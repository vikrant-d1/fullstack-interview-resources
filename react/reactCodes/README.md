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

**[⬆ Back to Top](#table-of-contents)**
