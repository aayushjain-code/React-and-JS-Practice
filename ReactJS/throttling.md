### Day-4-Throttling  (Throttle Message Send and Receive Display)

#### CodeSandbox Link : https://codesandbox.io/s/day-4-throttling-18jeii

Throttling  is a performance optimization technique to reduce the rate at which events trigger functions.

Throttling enforces a maximum number of times a function can be called over time.

## Implementing a throttle function
The throttle function is implemented using a timer that puts the throttled function on cooldown:
-Create a throttle function that accepts a callback and the cooldown duration arguments.
-The throttle function returns a new function, which when executed, stores the call arguments and starts the cooldown timer.
-When the timer finishes, execute the action with the cached arguments and clear them.

## Debounce vs. Throttle
Debounce waits for a function to have not been called for a given interval before it will execute the given function, or return the given value. Throttle will execute the given function, or return a value straight away, but only once for a given interval.


Frequent server API Calling.

Code Example: 
```
import { useState } from "react";
export default function App() {
  const [sentMessageText, setSentMessageText] = useState("");
  const [inputText, setInputText] = useState("");
  const [isButtonDisabled, setIsButtonDisabled] = useState(false);

  const throttle = (fun, delay) => {
    let run = false;
    return function (...args) {
      if (!run) {
        fun(...args);
        run = true;
        setTimeout(() => {
          run = false;
          setIsButtonDisabled(false);
        }, delay);
      }
    };
  };
  const handleChange = (e) => setInputText(e.target.value);
  const handleClick = throttle(() => {
    setIsButtonDisabled(true);
    setSentMessageText(inputText);
    setInputText("");
  }, 3000);

  return (
    <div className="App">
      <input type="text" value={inputText} onChange={(e) => handleChange(e)} />
      <button disabled={isButtonDisabled} onClick={(e) => handleClick(e)}>
        Print
      </button>
      {!isButtonDisabled && <h4>Message : {inputText}</h4>}
      {isButtonDisabled && <h4>Sent Message :{sentMessageText}</h4>}
    </div>
  );
}

```
