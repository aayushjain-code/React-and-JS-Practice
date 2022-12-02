### Day-3-Debouncing

#### CodeSandbox Link : https://codesandbox.io/s/day-3-debouncing-7mnmsv


Debouncing is a performance optimization technique to reduce the rate at which events trigger functions.

Very useful to improve the performance of large scale web applications.

Frequent server API Calling.

Code Example: 
```
import { useState } from "react";
export default function App() {
  const [name, setName] = useState("");

  function debounce(fn, delay) {
    let timer;
    return function (...args) {
      clearTimeout(timer);
      timer = setTimeout(() => fn(...args), delay);
    };
  }
  
  const handleChange = debounce((e) => {
    console.log(e.target.value);
    setName(e.target.value);
  }, 1000);

  return (
    <div className="App">
      <header className="App-header">
        <p> Search </p>
        <input type="text" onChange={(e) => handleChange(e)} />
        <p>{name}</p>
      </header>
    </div>
  );
}
```
Create a high-order function that takes as arguments:
    1. Callback function.
    2. Delay in ms.
then returns a new function that sets the timer to execute the callback after the timer done.

Catch here is every call of the function returned from the debounce function will cancel the previous timer using "cleartimeout(timer)" and start a new timer.

Reason: To insure that the callback function will be executed just once after the time that we passed as an argument in the last call.