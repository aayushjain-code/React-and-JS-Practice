## React-and-JS-Practice
### Day-2- Simple-to-do-App


#### CodeSandbox Link : https://codesandbox.io/s/day-2-simple-to-do-app-5ys5hw

```
import { useState } from "react";

export default function App() {
  const [item, updateItems] = useState(["Read"]);
  const [todo, setTodo] = useState("");

  const handleSubmit = (e) => {
    e.preventDefault();
    if (todo.length === 0 || !todo) return;
    setTodo("");
    updateItems([...item, todo]);
  };
  const handleCancel = (index) => {
    const newTodos = [...item];
    newTodos.splice(index, 1);
    updateItems(newTodos);
  };
  return (
    <div>
      <h1>To Do Application </h1>
      <input
        type="todo"
        value={todo}
        onChange={(e) => setTodo(e.target.value)}
      />
      <button onClick={(e) => handleSubmit(e)}>Submit</button>
      <ul>
        {item.map((data, index) => (
          <li key={index}>
            {data}
            <button onClick={() => handleCancel(index)}>Cancel</button>
          </li>
        ))}
      </ul>
    </div>
  );
 }
}
```