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

4. What is A/B testing in react?

- A/B testing in react is a technique used to compare two different versions of a web page or application and determine which version is more effective in achieving a specific goal. In React, A/B testing typically involves creating two or more versions of a component or a page, with each version having a slight variation in design, functionality, or content.

- The goal of A/B testing is to collect data on user behavior and preferences by randomly directing users to one of the variations and comparing the results. By comparing the performance of each version developers can identify which variation is more effective in achieving a specific goal, such as increasing conversions, improving user engagement, or reducing bounce rates.

- Overall A/B testing is a valuable tool for optimizing the user experience and improving the effectiveness of web pages and applications. It allows developers to make data-driven decisions and continuously improve the performance of their products.

---

5. How to do A/B testing in react?

- A/B testing is a popular technique used in web development to compare two versions of a web page to determine which one performs better in terms of achieving a particular goal, such as increasing user engagement or conversion rates.

- In reactjs, A/B testing can be implemented using various libraries or frameworks, but oen of the most popular and effective approaches is using a combination of React and Google Optimize.

- Here are the general steps to follow for A/B testing in ReactJS:

- `Define your goals and hypothesis`: Start by identifying the goals you want to achieve and forming a hypothesis about how changes to your web page could help achieve those goals. For example, if your goal is to increase user engagement, your hypothesis could be that changing the color of a call-to-action button will increase click-through rates.

- `Create variations of your web page`: Create multiple versions of your web page, each with a different element or design change that you want to test. For example, you could create two variations of your call-to-action button, one with a red color and the other with a blue color.

- `Integrate Google Optimize`: Integrate Google optimize into your react application. This will allow you to create experiments and track user behavior across multiple variations of your web page.

- `Difine experiment parameters`: Defien the parameters of your experiment, such as the percentage of users who will see each variation and the duration of the experiment.

- `Launch the experiment`: Launch your experiment and monitor the results using Google Optimize. After sufficient amount of data has been collected, analyze the results and determine which variation performed better in achieving your goals.

- `Implement the winning variation`: Implement the winning variation into your web page permanently.

---
