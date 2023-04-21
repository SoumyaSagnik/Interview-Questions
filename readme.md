# Interview Questions

`HTML` `CSS` `JavaScript` `React`

1. **What is div vs span or block vs inline?**

- `Block-level Elements`: A block level element always starts on a new line, and the browsers automatically add some space (margin) before and after the element. A block level element always takes up the full width available (100% of parent). Eg: div, p.

- `Inline Elements`: An inline element does not start on a new line. It takes up minimum space i.e., as much width as necessary. Eg: span

- The `div` element is block level and is often used as a container for other HTML elements.

- The `span` element is an inline container used to mark up a part of text, or document.

- Another important point to note is that an inline element cannot contain a block level element. Block elements can contain inline elements.

- However there are some exceptions to the above rule. Eg, the `a` tag, which is an inline element, can contain block level elements such as `div` or `p` if they are used within the `a` tag as an alternative to `href` attribute. This is known as the `block link` pattern.

- But in general, it is best practice to avoid nesting block level elements inside inline elements to ensure proper HTML structure and to avoid unexpected layout issues.

---

2. **What is inline-block? Difference between block, inline-block, and inline.**

- The three most common values for `display` property are: `block`, `inline-block`, and `inline`.

- `display: block`: Take up the entire space (width: 100%) of the parent by default. We can specify height and width to these elements. These elements always start in a new line. We can apply top and bottom margins.

- `display: inline-block`: Elements don't start in a new line. Their heights and widths can be specified. By default take take minimum space. We can apply top and bottom margins.

- `display: inline`: They don't start in a new line, take minimum space and we cannot apply height and width properties to them. Margin top and bottom doesn't work here.

---

3. **What is SCSS? How is it different from CSS? How does it get transpired to CSS?**

- SCSS (Sassy CSS) is a CSS `preprocessor` that adds functionality features to CSS. Differences are listed below:

- SCSS uses the same syntax as CSS, but allows for additinal features like `variables` and `nesting`.

- SCSS allows you to define variables that can be reused throughout your stylesheet, making it easier to maintain and update code.

- SCSS allows you to nest selectors, which can make your code more readable and easier to understand.

- `Mixin`: SCSS allows you to define reusable blocks of CSS code called mixins, which can be included in other parts of your code.

SCSS is not understood by the browser. It must be transpiled into CSS code that the browser can understand. This is typically done using a tool like `Webpack` or `Gulp`. Advantages of PostCSS over SCSS are listed below:

- PostCSS is a tool that processes CSS code and applies transformations to it. unlike SCSS, which is a preprocessor that extends CSS with additional features, PostCSS operates on standard CSS syntax and can be used to automate tasks like adding vendor prefixes, optimizing code, and generating fallbacks for older browsers.

- PostCSS works by using plugins, which are small JS modules that take in CSS code, apply transfromations to it, and output the transformed code.

- One of the key benefits of PostCSS over SCSS is its flexibility. Since it operates on standard CSS syntax, it can be used with any CSS code. This makes it easy to integrate into existing projectsm and it allows you to apply the same transformations to both preprocessed and hand-written CSS code.

- Aditionally, PostCSS can be faster than SCSS because it doesn't require compiling a separate file to generate the final CSS code. Instead, PostCSS operates directly on the CSS code, which can result in faster build times and a more efficient development workflow.

---

4. **What are positions in CSS? Differentiate between them.**

- Positions in CSS are listed below:

- Static: `This is the default position` value for all HTML elements. Elements with a static position are positioned according to the normal document flow, and the top, left, bottom, right and z-index properties have no effect on them.

- Relative: Elements with a relative positoin are positioned `relative to their normal position` in the document flow. You can use the top, right, bottom, and left properties to move them in any direction relative to their original position.

- Absolute: Elements with an absolute position are positioned relative to their closest positioned ancestor. If there is no positioned ancestor, the element is positioned relative to the initial containing block. `Element positioned absolute is taken out of the normal document flow`. This means that other elements will not be affected by its position, and it may overlap with other elements on the page. You can use the top, left, bottom, right properties to postion them relative to their closest positioned ancestor (element with position relative).

- Fixed: Elements with a fixed position are positioned relative to the viewport, and they do not move when the page is scrolled. You can use the top, left, right, and bottom properties to position them relative to the viewport. `Element positioned fixed is taken out of the normal document flow`.

- Sticky: Elements with a sticky position are positioned based on the user's scroll position. They behave like a combination of `relative` and `fixed` positioning. They start out in the normal document flow (relative), but they become `fixed` once the user has scrolled to a certain point. You can use the top, left, bottom, and right properties to set the sticky position.

- Inherit: Elements with an inherit position will inherit the position value of their parent element. If the parent element does not have a position value set, the element will be `static`

- `Relative vs Absolute`: Element positioned absolute is taken out of the normal document flow. This means that other elements will not be affected by its position, and it may overlap with other elements on the page. In contrast, element with relative positioning is still in the normal document flow and will occupy space, and other elements will be affected by its position. Another difference is that element positioned absolute will be positioned wrt it's nearest parent having position relative or the html element if none of its parents are positioned relative. Elements positioned relative will be positioned wrt to its own original position when properties like top, bottom, left, and right are used on it.

- `Fixed vs Sticky`: Element positioned fixed remains in the same position relative to the viewport and is taken out of the normal document flow from the beginning. Element positioned sticky is a combination of relative and fixed position. Initially, sticky element behaves like an element positioned relative. As soon as the user scrolls and the element is about to be out of view, the sticky element behaves like fixed element.

- `Absolute vs Fixed`: Element positioned absolute is positioned relative to its nearest parent having position relative or html in case there are no parents with position relative. Elements positoined fixed are positioned wrt the viewport. This means that element positoined fixed will remain in view, no matter how much we scroll down the page, in the exact same position. But the element positioned absolute will not be visible to us once we scroll down enough.

---

5. **Explain CSS Specificity.**

- In CSS, specificity is the measure of how specific a selector is in selecting an element or group of elements on a web page. Specificity is determined by the number and type of selectors used in the CSS rule, `and it determines which CSS rule is applied to an element when multiple rules target the same element`.

- Each `id` selector increases the specificity by `100`. Each `class/ attribute/ pseudo class` selector increases specificity by `10`. Each `tag/ element` selector increases the specificity by `1`. CSS rule having the highest specificity is applied to the concerned element.

- Precedence order: !important > inline-css > id > class > tag.

---

6. **What is the difference between Reset CSS and Normalize CSS?**

- By default, different web browsers may have slightly different styles for HTML elements like headings, paragraphs, lists, and links. This can make it difficult to create consistent styles across different browsers.

- `Reset CSS` resets all the styles for all HTML elements to a consistent baseline. This means that developers need to define all styles for all elements. It is a good choice for developers who want complete control over the styles of all elements.

- `Normalize CSS` is a more conservative approach that poreserves some of the default styles for HTML elements while normalizing others. It provides a set of CSS rules that make HTML elements consistent across different browsers, but still allows developers to define their own styles without having to completely redefine every element. It is a good choice for developers who want a more consistent baseline of styles without having to start from scratch.

- The infamous three lines actually comes under CSS Reset.

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

---

7. **Differentiate between let, var, and const.**

- `Scope`: let and const are block scoped, while var is function scoped.

```javascript
for (var i = 1; i < 4; i++) {
  setTimeout(() => {
    console.log(i);
  }, 1000);
}
// Output: 4 4 4
```

```javascript
for (let i = 1; i < 4; i++) {
  setTimeout(() => {
    console.log(i);
  }, 1000);
}
// Output: 1 2 3
```

- `Hoisting`: all the three are `hoisted`. However, `let` and `const` are in a `temporal dead zone`. This means that JavaScript acknowledges its presence by providing it with the value `undefined` but `won't let us use it`. We would be getting the value `undefined` when we access var before its declaration.

```javascript
console.log(a);
var a; // undefined
```

```javascript
console.log(b); // ReferenceError: b is not defined
let b;
```

```javascript
console.log(c); // ReferenceError: c is not defined
const c = 30;
```

- `Global Object`: var gets attached to the global object when declared in the global space, while let and const do not get attached to the global space.

```javascript
var a = 10;
let b = 20;
const c = 30;

console.log(a); // 10
console.log(b); // 20
console.log(c); // 30

console.log(this.a); // 10
console.log(this.b); // undefined
console.log(this.c); // undefined

console.log(window.a); // 10
console.log(window.b); // undefined
console.log(window.c); // undefined
```

- `Re-declaration`: we can re-declare var in the same scope with the same variable name. This is not possible with let and const.

```javascript
var a = 10;
var a = 20;
console.log(a);

let b = 10;
let b = 20; // SyntaxError: Identifier 'b' has already been declared

const c = 10;
const c = 20; // SyntaxError: Identifier 'c' has already been declared
```

- `Update`: we can update the values in case of var and let, but in case of const it is not possible.

```javascript
var a = 10;
a = 20;
console.log(a); // 20

let b = 10;
b = 20;
console.log(b); // 20

const c = 10;
c = 20; // TypeError: assignment to constant variable.
```

- `Initialization`: in case of const, we've to initialize the variable in the same line where it is declared. var and let can be initialized later.

```javascript
var a;
a = 10; // 10

let b;
b = 10; // 10

const c;
c = 10; // SyntaxError: Missing initializer in const declaration
```

- `Shadowing`: When we have the same variable name in different places, the value of the variable closest to the line of execution is chosen. This phenomenon is called shadowing.

```javascript
var a = 10;
const b = 20;
let c = 30;

{
  var a = 100;
  const b = 200;
  let c = 300;
  console.log(a); // 100
  console.log(b); // 200
  console.log(c); // 300
}

console.log(a); // 100
console.log(b); // 20
console.log(c); // 30
```

- In case of var, shadowing is permanent. This is because var is function scoped and gets attached to the global object. So a variable having the same name within a block and outside would point to the same location in the global object.

- var can be used to shadow let and const, but let or const cannot be used to shadow var. This is because var is not block scoped. Hence it exists outside the block as well and we know from above that let and const cannot have same variable name redeclared in the same scope.

```javascript
var a = 10;
{
  let a = 20;
  console.log(a); // 20
}
console.log(a); // 10
```

```javascript
let a = 10;
{
  var a = 20; // SyntaxError: Identifier 'a' has already been declared
}
```

---

8. **What is a Promise? What is Promsie Chain?**

`Promise`

- A promise is an object that represents the eventual completion or failure of an asynchronous operation. Essentially, a promise is an object returned by an async operation to which we attach callbacks instead of passing the callback to another function.

The promise object has three states: `Pending`, `Fulfilled`, and `Rejected`.

- `Pending`: The initial state of a Promise before it has been resolved or rejected.

- `Fulfilled`: The state of a Promise when it has been resolved, meaning that the value it represents is now available.

- `Rejected`: The state of a Promise when it has been rejected, meaning that an error has occured and the value it represents is not available.

A promise has two important methods:

- `then()`: This method is used to handle the fulfullment of a Promise. It takes two arguments: a callback function that will be executed when the Promise is resolved, and an optional callback function that will be executed if the promise is rejected.

- `catch()`: This method is used to handle the rejection of a Promise. It takes one argument: a callback function that will be executed if the Promise is rejected.

```javascript
function fetchData() {
  return fetch("https://example.com/data")
    .then((response) => {
      if (!response.ok) {
        throw new Error("Network error");
      }
      return response.json();
    })
    .catch((error) => {
      switch (error.message) {
        case "Network error":
          console.log("There was a network error");
          break;
        case "JSON parse error":
          console.log("There was a problem parsing the JSON data");
          break;
        default:
          console.log("An unknown error occured");
      }
    });
}
```

Advantages of promises:

- Promise is immutable. So there is no possibility of altering the data we received from an asynchronous event.
- Promise allows us to avoid `inversion of control` and `pyramid of doom`.

- First we have to understand that before promises, people used to pass callbacks to another function in order to perform async operations. This caused `inversion of control` and `pyramid of doom`.

- `Inversion of Control`: When we pass a function to another function as callback, the function passed as callback is completely at the mercy of the function to which it is passed. We cannot call the callback function directly. Hence we lose control over a certain portion of our code. This situation is known as inversion of control. While using promises, we have the `then()` which resolves this issue.

- `Pyramid of Doom`: Also known as `callback hell`, this happens when we chain too many interdependent async operations. There will be callback inside a function, the callback will have another callback, and this continues. This results in the code growing horizontally instead of vertical, and this structure is known as the Pyramid of Doom.

`Promise Chain`

- A Promise Chain is a sequence of asynchronous operations that are executed one after the other, with each operation waiting for the previous one to complete before starting.

```javascript
function promiseChain(data) {
  operation1(data)
    .then((data2) => {
      return operation2(data2);
    })
    .catch((error) => {
      console.log(error.message);
    })
    .then((data3) => {
      return operation3(data3);
    })
    .catch((error) => {
      console.log(error.message);
    });
}
```

---

9. **Output Questions**

```javascript
function promisify(number, increase) {
  return new Promise((resolve) =>
    setTimeout(() => resolve(number * 2 + increase), 100)
  );
}

async function double(number, increase) {
  const value = await promisify(number, increase);
  return value;
}

async function run() {
  let result;
  result = await double(5, 0);
  result = await double(10, result);
  result = await double(20, result);
  console.log(result);
}
run();

// Output: 70
```

```javascript
for (var i = 1; i <= 3; i++) {
  (function (index) {
    setTimeout(function () {
      console.log(index);
    }, i * 1000);
  })(i);
}

// Output: 1 2 3
```

```javascript
for (var i = 1; i <= 3; i++) {
  setTimeout(function () {
    console.log(i);
  }, i * 1000);
}

// Output: 4 4 4
```

```javascript
for (var i = 1, j = 1; i <= 3; i++, j++) {
  setTimeout(
    function () {
      console.log(this);
    }.bind(i),
    j * 100
  );
}

// Output: Number {1} Number {2} Number {3}
```

```javascript
let x = true;
let count = 0;
setTimeout(() => {
  x = false;
}, 2000);

while (1) {
  if (x) {
    count++;
    console.log(count);
  }
}

// Output: infinite loop
/* JS is a single threaded language. The while loop will block the
callstack and the setTimeout will remain in the callback queue, starving
to be put to the callstack for execution.
```

---

10. **If there are two functions to be executed, one is a returned promise and the other is a function inside the setTimeout. Which will be executed first given the call stack is busy and both are ready to be executed when the call stack becomes free?**

- The `promise` will be given `priority` over the `setTimeout` function. In JavaScript, the event loop is responsible for managing the call stack, callback queue and the microtask queue. Promises and operations from mutation observer go to the microtask queue while all other asynchronous operations are passed to the callback queue till they're ready to be executed in the callstack.

- The event loop keeps on monitoring all three: callstack, callback queue, and the microtask queue. If there is something waiting in the callback queue or the microtask queue to be executed, it is the event loop which checks if the callstack is free and then it pushes the pending task of the callback/ microtask queue to the callstack. Everything in JS is executed inside the callstack.

- Now it is given to us that the call stack was busy and the promise has been brought to the microtask queue and the setTimeout function has been brought to the callback queue. `Microtask queue has higher priority than the callback queue`. Hence the event loop picks up the promise and sends it to the callstack, hence it is executed first. After that, the callback from setTimeout is executed.

---

11. **Explain the useMemo hook in react.**

- The useMemo hook accepts a callback function and a list of dependencies as parameters, and returns the `memoized` value returned by the passsed function. The callback passed to the useMemo hook will only be executed if any value passed in the dependency array changes. `It is useful to avoid expensive calculations on every render when the returned value is not going to change.`

```javascript
const App = () => {
  const [dark, setDark] = useState(false);
  const [value, setValue] = useState(1);
  const doubleNumber = useMemo(() => slowFunction(value), [value]);

  const styles = useMemo(() => {
    return {
      backgroundColor: dark ? "black" : "white",
      color: dark ? "white" : "black",
    };
  }, [dark]);

  useEffect(() => {
    console.log("useEffect called");
  }, [styles]);

  function handleValueChange(e) {
    setValue(e.target.value);
  }

  function handleThemeChange() {
    console.log("Theme change called");
    setDark((prevDark) => !prevDark);
  }

  function slowFunction(value) {
    console.log("Slow function called");
    for (let i = 0; i < 1000000000; i++) {}
    return value * 2;
  }

  return (
    <>
      <input type="number" value={value} onChange={handleValueChange} />
      <button onClick={handleThemeChange}>Change Theme</button>
      <div style={styles}>{doubleNumber}</div>
    </>
  );
};
```

- In the above code, we have an input tag, a button and a div that shows 2x value of the input tag. We've used the useMemo hook in two places here. One where the value passed in dependency array is `primitive` and other where it is a `reference`. The `slowFunction` slows down the code by iterating over a long number, doing nothing. If we don't use the useMemo hook, this function will be called everytime the component rerenders, and the component will re-render everytime any state in the component changes.

- As you can see, the `slowFunction` has nothing to do with changing the `dark` state. Hence we've memoized the `slowFunction`, which will now run only when the `value` state changes. It won't run if we change the `dark` state in our application anymore.

- For the second part, we're memoizing the `styles` object. Here we're checking for `referential equality`. Basically, the `styles` object is formed everytime the component re-renders and even if the value inside it is same, the code inside the `useEffect` would be executed everytime if we don't use `useMemo` since a new object is created everytime and objects point to a particular location, which is compared, rather than what's inside the object. Hence we're memoizing the `styles` object itself such that the code inside useEffect runs only when the value of the `dark` state changes, which in turn would change the `styles` object.

---

12. **Explain the useCallback hook in react.**

- The useCallback hook returns a `memoized callback` when passed a function and a list of dependencies as parameters. It is useful when a component is passing a callback to its child component to prevent the re-rendering of the child component when not required.

- The major diffrence between `useCallback` and `useMemo` is that useCallabck returns a `memoized function` which can later be called. useMemo, on the other hand returns a `memoized value`.

```javascript
// App.jsx

import { useState, useCallback } from "react";
import List from "./List";

const App = () => {
  const [value, setValue] = useState(1);
  const [isLight, setIsLight] = useState(true);
  const styles = {
    backgroundColor: isLight ? "white" : "yellow",
  };

  const getValueList = useCallback(
    (incrementor) => {
      return [
        value + incrementor,
        value + 1 + incrementor,
        value + 2 + incrementor,
      ];
    },
    [value]
  );

  function handleClick() {
    setIsLight((prevValue) => !prevValue);
  }

  function handleValueChange(e) {
    setValue(parseInt(e.target.value));
  }

  return (
    <div style={styles}>
      <input type="number" value={value} onChange={handleValueChange} />
      <button onClick={handleClick}>Toggle Theme</button>
      <List getValueList={getValueList} />
    </div>
  );
};

export default App;
```

```javascript
// List.jsx

import { useState, useEffect } from "react";

const List = ({ getValueList }) => {
  const [items, setItems] = useState([]);
  useEffect(() => {
    setItems(getValueList(3));
    console.log("updating items");
  }, [getValueList]);

  return items.map((item) => <div key={item}>{item}</div>);
};

export default List;
```

- In the above code, we have parent App.jsx and child List.jsx. Parent component has a function `getValueList` that returns a list of items which is to be passed to the child component. If we don't use the `useCallback` hook, the `useEffect` inside the child component will be executed everytime the parent re-renders since everytime a new function is being created in the parent, which will always be different `(referential equality)`. In order to get around this, we have `memoized` the `getValueList` function by placing it inside the `useCallback` hook, and since the `getValueList` function returns a list which dependes only on the `value` state, we have the `value` state inside the dependency array. Now the `useEffect` will not be executed if we change the `isLight` state in the parent component, thus optimizing the app.

---

13. **What are pure components in react?**

- A pure component is a component that that does not re-render when the value of state and props associated with it has been updated with the same values. Pure component restricts re-rendering, ensuring higher performance of the component.

```javascript
import React from "react";

const PureComponent = React.memo((props) => {
  return <div>{props.text}</div>;
});

export default PureComponent;
```

- `React.memo` is a higher-order component that memoizes the output of a component and caches it based on its props. It is used to optimize rendering performance by avoiding unnecessary re-renders of a component when its props have not changed.

- `Use Pure Components when props and state changes are made to primitives. State and prop changes to a reference may lead to incorrect results and inconsistent rendering.`

---

14. **What is the virtual dom in react?**

- React maintains a clone of the real DOM (Document Object Model) which is called the virtual DOM. Whenever there's an update, react creates a new version of the virtual DOM.

- It then compares the two versions of the virtual DOM and calculates the shortest path to make those changes. This process of comparison of the old and new versions of the virtual DOM is called `diffing`.

- The shortest path obtained is then used by react to update the real DOM with minimum changes. This entire process is called `reconciliation`.

---

15. **What are the lifecycle methods in a class component?**

- We can mainly classify the methods into four phases: `Mounting` `Updating` `Unmounting` `Error Handling`.

- `Mounting`: The mounting lifecycle methods are called when an instance of a component is being created and inserted to the DOM. During the mounting phase, we have four methods: `constructor` `static getDerivedStateFromProps` `render` `componentDidMount`.

- `Updating`: The updating lifecycle methods are called when a component is being re-rendered as a result of changes to either its props or state. During the updating phase, we have 5 methods: `static getDerivedStateFromProps` `shouldComponentUpdate` `render` `getSnapshotBeforeUpdate` `componentDidUpdate`.

- `Unmounting`: The unmounting lifecycle methods are called when a component is being removed from the DOM. During the unmounting phase we have 1 method: `componentWillUnmount`.

- `Error Handling`: The error handling methods are called when there's an error during rendering, in a lifecycle method, or in the constructor of any child component. During error handling, we have 2 methods: `static getDerivedStateFromError` `componentDidCatch`.

---

16. **Why redux uses immutable objects?**

- Redux objects are made immutable for the following reasons:

- Predictability: By making redux objects immutable, the state of the application becomes predictable. When an action is dispatched to the store, the state is updated by returning a new object with the updated properties, rather than mutating the existing object. This means that the state of the application can be tracked and easily tracked back to the source of the changes.

- Performance: By using immutable objects, the performance of the application can be improved, particularly when working with large data sets. Because immutable objects can be shared between different parts of the application without worrying about them being mutated, unnecessary copies of data can be avoided, leading to faster perfromance.

- Debugging: Debugging can be easire with immutable objects because they allow you to easily trace the state of the application back to the source of the changes.

---

17. **What is the `this` keyword in JavaScript?**

- The `this` keyword in JavaScript referes to the object that is currently executing the code. At the global level, this points to the global object, which is `window` in case of browsers.

```javascript
console.log(this === window); // true
```

```javascript
function check() {
  console.log(this === window); // true
}

check();
```

```javascript
class Check {
  constructor() {
    console.log(this === window); // false
  }
}

const checker = new Check();
```

`When this appears inside a function that is not bound to any object or class, the value of this defaults to the global object`.

---

18. **Why are meta tags used? What are the meta tags you know?**

- Meta tags are used in HTML to provide additional information about a web page to search engines, social media platforms, and web browsers. They help in `Search Engine Optimization`. They are placed in the head section of an HTML document and are not visible on the web page itself. Some common meta tags are listed below:

- `<meta charset="utf-8">`: Specifies the character encoding of the HTML document.

- `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Sets the viewport width and initial zoom level for mobile devices.

- `<meta name="description" content="...">`: Provides a short description of the web page that can be displayed in search engine results.

- `<meta name="keywords" content="...">`: Specifies the keywords or phrases that the web apge is related to.

- `<meta name="robots" content="...">`: Instructs search engines how to crawl and index the web page.

- `<meta name="author" content="...">`: Specifies the author of the web page.

- `meta name="theme-color" content="..."`: Sets the color of the browser toolbar and browsers's UI when the user is on the web page.

---

19. **How can you improve SEO just by HTML tags?**

- `Use relevant and descriptive title tags`: The title tag is one of the most important HTML tags for SEO. Make sure your title tag accurately reflects the content of your page and includes your target keywords.

- `Use header tags to structure your content`: Header tags help to organize content and make it more readable. Use header tags to break your content into logical sections and include your target keywords in the headings.

- `Use meta descriptions to provide a summary of your content`: Meta descriptions appear in search engine results and can help to improve click-through rates.

- `Use alt tag to describe your images`: Alt tags are used to describe images for people with visual impairments and for search engines.

- `Do not used span and div tags everywhere`: Use Semantic HTML wherever possible

---

20. **Explain the box model in CSS.**

- The box model has four parts: `Content` `Padding` `Border` `Margin`

- `Content`: This is the actual content.

- `Padding`: This is the space between the content and the border of the box.

- `Border`: This is a line that surrounds the padding and content of the box.

- `Margin`: This is the space between the border of the box and the neighbouring elements on the page.

---

21. **Explain box-sizing property in CSS.**

- The `box-sizing` property controls how the `total size of an element is calculated`, including its content, padding, and border. The possible values for box-sizing are:

- `content-box`: This is the default value. It tells the browser to `calculate the size of an element based on its content only, without including padding or border`. In other words, the size of an element is determined by the width and height properties.

- `border-box`: It tells the browser to calculate the size of an element based on `its content, padding, and border`. In other words, the width and height properties specify the size of the content area, and the padding and border are added to it. This is more convenient because it lets us set the width and height of an element without having to take into account the padding and border.

---

22. **What are the call, bind, and apply methods in JavaScript? Differentiate between them.**

- `call` `bind` and `apply` are used to manipulate the `this` keyword and pass arguments to functions in different ways.

- Whenever we call a function, by default js behind the scene uses the `call` method. When we have a function defined inside an object, and we want to reuse the function inside that object in another object, we use `call` `bind` and `apply`.

- `call` and `apply` **invoke the function immediately**, while **bind returns a function that can be invoked later**.

```javascript
function helloWorld() {
  console.log("Hello World");
}

helloWorld();
helloWorld.call();
helloWorld.apply();

// the above three lines will log the same output.
// JS by default uses .call() to call a function.
```

```javascript
let participant1 = {
  name: "John",
  battery: 70,
  chargeBattery: function () {
    this.battery = 100;
  },
};

let participant2 = {
  name: "Doe",
  battery: 30,
};

console.log(participant1.battery); // 70
participant1.chargeBattery();
console.log(participant1.battery); // 100

console.log(participant2.battery); // 30
participant1.chargeBattery.call(participant2);
console.log(participant2.battery); // 100
```

```javascript
let participant1 = {
  name: "John",
  battery: 70,
  chargeBattery: function (p1, p2) {
    this.battery = this.battery + p1 + p2;
  },
};

let participant2 = {
  name: "Doe",
  battery: 30,
};

console.log(participant2.battery); // 30
participant1.chargeBattery.call(participant2, 10, 20);
console.log(participant2.battery); // 60
```

- While using the `call` method, the first argument is `this`, followed by `n arguments`.

```javascript
let participant1 = {
  name: "John",
  battery: 70,
  chargeBattery: function (p1, p2) {
    this.battery = this.battery + p1 + p2;
  },
};

let participant2 = {
  name: "Doe",
  battery: 30,
};

console.log(participant2.battery); // 30
participant1.chargeBattery.apply(participant2, [10, 20]);
console.log(participant2.battery); // 60
```

- While using the `apply` method, the first argument is `this`, `followed by an array of n arguments`.

```javascript
let participant1 = {
  name: "John",
  battery: 70,
  chargeBattery: function (p1, p2) {
    this.battery = this.battery + p1 + p2;
  },
};

let participant2 = {
  name: "Doe",
  battery: 30,
};

let participant3 = {
  name: "Sally",
  battery: 25,
};

console.log(participant2.battery); // 30
const newBattery2 = participant1.chargeBattery.bind(participant2, 10, 20);
newBattery2();
console.log(participant2.battery); // 60

console.log(participant3.battery); // 25
const newBattery3 = participant1.chargeBattery.bind(participant3, ...[10, 20]);
newBattery3();
console.log(participant3.battery); // 55
```

- `bind` returns a function that can be invoked later instead of invoking the function immediately. The first parameter is `this`, followed by `n arguments`. However, we can also pass an `array of n arguments preceeded by spread operator` as shown in the example above.

- Differences are listed below:

- `call` and `apply` invoke the function immediately, while `bind` returns a function that can be invoked later.

- `call` has second argument as `n parameters`, `apply` has second argument as `array of n parameters`.

---
