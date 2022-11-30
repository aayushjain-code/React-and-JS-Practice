

## Day-1- React-and-JS-Practice

### Fetch an API with Axios & Fetch

#### CodeSandbox Link : https://codesandbox.io/s/day-1-simple-fetching-data-muvllb

```
import axios from "axios";
import { useEffect, useState } from "react";
import "./styles.css";

const givenUrl = "https://jsonplaceholder.typicode.com/users";
export default function App() {
  const [Users, fetchUsers] = useState([]);

  const getDataWithFetch = () => {
    fetch(givenUrl)
      .then((response) => response.json())
      .then((json) => {
        console.log(json);
        fetchUsers(json);
      });
  };

  const getDataWithAxios = async () => {
    const res = await axios.get(givenUrl);
    console.log(res);
    fetchUsers(res.data);
  };

  useEffect(() => {
    // getDataWithAxios()
    getDataWithFetch();
  }, []);
  
  return (
    <>
      <h1>Data:</h1>
      {Users.map((user) => {
        return (
          <div key={user.id}>
            <p>{user.name}</p>
          </div>
        );
      })}
    </>
  );
}
```