### Day-5 Simple Example of Memoization Using Square. 

#### CodeSandbox Link : https://codesandbox.io/s/day-5-memoization-b8yg06

👉 What is Memoization 💭 ? How and When to Memoize in JavaScript🔆?

⚙️ Memoization is an optimization technique that can help make heavy computation processes more efficient.

⚙️ Can help speed up our code, especially when dealing with repetitive and heavy computing functions. Makes applications more efficient and hence faster.

🎯 Concept Behind Memoization
It does this by storing computation results in a cache(temporary data store) and retrieving that same information from the cache the next time it's needed instead of computing it again.

🔑 Every time our memoize method is executed, one of two things can occur:

1️⃣ If the input has been used before, locate it in the cache and immediately return the value stored without executing any further computations.

2️⃣ Use the input to execute any necessary computations, store the results in the cache, and return the result.

If the input has been used before, locate it in the cache and immediately return the value stored without executing any further computations.

Use the input to execute any necessary computations, store the results in cache, return the result.

Code Example: 

```

function squared(number) {
  //Added A Fake Expesive Operation for checking...
  for (let i = 0; i < 50000; ++i);
  return number * number;
}

function memoize(cbFunc) {
  let cache = {};
  return (...args) => {
    let argsKey = JSON.stringify(args);
    if (!cache[argsKey]) {
      cache[argsKey] = cbFunc(...args);
    }
    return cache[argsKey];
  };
}

const memoizedSquare = memoize(squared);

console.time("First call");
console.log(memoizedSquare(2)); //returns 4
console.timeEnd("First call"); // First call: 2.281005859375 ms

console.time("Memoised Second call");
console.log(memoizedSquare(2)); // returns cached value 4
console.timeEnd("Memoised Second call"); // Memoised Second call: 0.031005859375 ms


```
