1. How to pass data from child to parent?

By calling the prop passed to the child element as a function. The function will be present in the parent component.

```javascript
// App.jsx

import { useState } from "react";
import "./App.css";
import Child from "./Child";

const App = () => {
  const [count1, setCount1] = useState(0);
  const [count2, setCount2] = useState(0);
  const [count3, setCount3] = useState(0);
  function clicked(type) {
    switch (type) {
      case 1:
        setCount1((prevCount) => prevCount + 1);
        break;
      case 2:
        setCount2((prevCount) => prevCount + 1);
        break;
      case 3:
        setCount3((prevCount) => prevCount + 1);
        break;
      default:
        return;
    }
  }

  return (
    <div>
      <Child clicked={clicked} type={1} count={count1} />
      <Child clicked={clicked} type={2} count={count2} />
      <Child clicked={clicked} type={3} count={count3} />
    </div>
  );
};

export default App;
```

```javascript
// Child.jsx

const Child = ({ clicked, count, type }) => {
  return (
    <div>
      <button onClick={() => clicked(type)}>Click</button>
      <div>{count}</div>
    </div>
  );
};

export default Child;
```

In the above example, there are 3 different buttons, each having a count, and each button's count increases once it's clicked.

---

2. Differentiate between state and props.

| Props                                   | State                                                  |
| --------------------------------------- | ------------------------------------------------------ |
| Props are immutable                     | State can be changed                                   |
| Props get passed to the child component | State is managed within the component                  |
| Props are like function parameters      | State is like a variable declared in the function body |

---

3. What are reducers in redux?

- Reducers are functions that are responsible for updating the state of your application in response to actions that have been dispatched. A reducer function takes in two arguments: the current state and an action object.

- Reducers in redux toolkit use thhe `slice reducer` pattern, which means that each slice of state has its own separate reducer function. This makes it easier to manage large and complex state trees, as each slice can be updated independently.

---
