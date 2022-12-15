### Day-16 React's strategy to compute minimal DOM operations when re-rendering the UI.⚛️ Virtual DOM?

 👋 React's strategy to compute minimal DOM operations when re-rendering the UI.⚛️ Virtual DOM?

Virtual DOM is just a copy of the original DOM kept in the memory and synced with the actual DOM 
by libraries such as React DOM. This process is called Reconciliation.

React is fast because of its Virtual DOM. It renders everything in JavaScript and then changes only the things changed in the actual DOM.

What happens when you try to update the DOM in React?
1. The entire virtual DOM gets updated.
2. The virtual DOM gets compared to what it looked like before you updated it.
3. React figures out which objects have changed.
4. The changed objects, and the changed objects only, get updated on the real DOM.
5. Changes on the real DOM cause the screen to change.
