### Day-6 UseMemo- “remember” a computed value between renders. 

#### CodeSandbox Link : https://codesandbox.io/s/day-6-usememo-v3p57w

👉 UseMemo- “remember” a computed value between renders. 🔆?

⚙️ Each re-render is a snapshot 📸 of what the application's UI should look like 👰‍♀️ at a given moment in time, based on the current application state.

⚙️ Each “re-render” produces picture 🤳 of what the DOM should look like, based on the current state.

👉 By re-rendering, React creates a new snapshot, and it “find the differences” and figures out what needs to change. 

🎯 Re-renders aren't a big deal. But, in certain situations, these snapshots do take a while to create. This can lead to performance problems, like the UI not updating quickly enough after the user performs an action.

useMemo to resucue:
1️⃣ Reducing the amount of work that needs to be done in a given render.
2️⃣ Reducing the number of times that a component needs to re-render.


Code Example: 

```
import React, { useState, useMemo } from "react";
function fibonacci(x) {
  if (x <= 0) return 0;
  if (x === 1) return 1;
  return fibonacci(x - 1) + fibonacci(x - 2);
}

const App = () => {
  const [number, setNumber] = useState(1);
  const fib = useMemo(() => fibonacci(number), [number]);

  return (
    <>
      <h2>
        Fibonacci of {number} is 👉 {fib}
      </h2>
      <button onClick={() => setNumber(number + 1)}>+</button>
    </>
  );
};

export default App;
```
