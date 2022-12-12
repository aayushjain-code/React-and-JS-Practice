### Day-13 Are you importing components like ../../../Components/Dashboard/Profile in React

 👋 Are you importing components like ../../../Components/Dashboard/Profile in React ⚛️?

The Problem with ../../../ imports:
- you would need to update all of your imports in your project and add one extra ../ to all of your imports.
- Hard to refactor.
- It becomes worse as you get further deeper into it.
- You need to change the entire codebase if you need to extract the code to be used externally as an NPM module.

Benefits of Absolute Import:
-You can move your existing code to other components with imports without any changes.
-You can directly copy/paste code from a component and use it anywhere else without making any changes to the imports.
-Using the import path, you can quickly identify where the component is actually placed.
-Cleaner Code.
-Easier to write.


Code Example: 

```
// Without Absolute Import

import React from "react";
import Button from "../../Button/Button";
import { LINKS, STRINGS } from "../../../utils/constants";
import styles from "./App.module.css";

function App() {
  return (
    <div className={styles.App}>
      <Button>{STRINGS.HELLO}</Button>

      <a href={LINKS.HELP}>Learn more</a>
    </div>
  );
}

export default App;
-------------------------------------------------------------
// With Absolute Import 

import React from "react";
import { LINKS, STRINGS } from "utils/constants";
import Button from "components/Button/Button";
import styles from "./App.module.css";

function App() {
  return (
    <div className={styles.App}>
      <Button>{STRINGS.HELLO}</Button>

      <a href={LINKS.HELP}>Learn more</a>
    </div>
  );
}

export default App;
```
