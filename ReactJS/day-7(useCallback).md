### Day-7 useCallback- Avoid unnecessary re-renders with useCallback

#### CodeSandbox Link : https://codesandbox.io/s/day-7-usecallback-s2z2pj

👉 Avoid unnecessary re-renders with useCallback ! 🔆

⚙️ Usage
    🏃‍♀️ Skipping re-rendering of components
    🎊 Updating state from a memoized callback
    🔥 Preventing an Effect from firing too often
    🛠️ Optimizing a custom Hook     


⚙️ By default, when a component re-renders, React re-renders all of its children recursively..

👉 By wrapping a function in useCallback, you ensure that it’s the same function between the re-renders (until dependencies change).  

🎯 The difference between useMemo and useCallback.
    👉 useMemo caches the result of calling your function
    👉 useCallback caches the function itself. Unlike useMemo, it does not call the function you provide. Instead, it caches the function you provided.


Code Example: 

```
import React, { useState, useCallback } from "react";

export default function App() {
  const [count, setCount] = useState(0);

  const onClick = useCallback((c) => {
    console.log("update!");
    setCount(c);
  }, []);

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => onClick(count + 1)}>Increase Count</button>
    </div>
  );
}
```
