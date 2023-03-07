1. Implement your version of queue.

```javascript
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(element) {
    this.items.push(element);
  }

  dequeue() {
    if (this.isEmpty()) return "Underflow";
    return this.items.shift();
  }

  front() {
    if (this.isEmpty()) return "No elements in queue";
    return this.items[0];
  }

  isEmpty() {
    return this.items.length === 0;
  }

  printQueue() {
    let str = "";
    for (let i = 0; i < this.items.length; i++) {
      str += this.items[i] + " ";
    }
    return str.trim();
  }
}
```

---

2. Given a nested array [1, 2, 3, [4, 5, [6, 7], 8], 9, 10], flatten it.

```javascript
const nestedArray = [1, 2, 3, [4, 5, [6, 7], 8], 9, 10];

function flattenArray(arr) {
  return arr.reduce((acc, curr) => {
    return Array.isArray(curr)
      ? acc.concat(flattenArray(curr))
      : acc.concat(curr);
  }, []);
}

const flattenedArray = flattenArray(nestedArray);
console.log(flattenedArray); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

---

3. Differentiate between map and forEach.

- map is used to perform certain action on each element of an array. It returns a new array with the results of calling a provided function on every element of the original array. It doesn't change the original array.

- forEach is used to iterate over an array. It doesn't return anything.

---

4. Differentiate between null and undefined. What will be the result of null == undefined and null === undefined?

- null is an explicit value that represents 'nothing' or 'no value'. It is used to indicate that a variable or object property has intentionally been set to a non-value.

- undefined is a special keyword that is assigned to variables during the memory creation phase of the execution context. The variables will have undefined assigned to them until we initialize them with some value.

- null == undefiend will return **true**.

- null === undefined will return **false**.

---

5. Explain event delegation.

- Event delegation is a technique in JavaScript that allows us to attach event listeners to parent element, instead of attaching each child of the parent element with a separate event listener.

- It is useful when there's a large number of child elements. It comes handy even while working with dynamic content where child elements are being added to the parent at runtime.

```javascript
const parent = document.querySelector(".parent");

parent.addEventListener("click", (e) => {
  if (e.target.classList.contains("child")) {
    console.log("Child Clicked");
  }
});
```

---

6. What will be the output of the following code snippet?

```javascript
function a() {
  for (var i = 0; i < 3; i++) {
    setTimeout(function log() {
      console.log(i);
    }, i * 1000);
  }
}

a();

//Output: 3 3 3

function b() {
  for (let j = 0; j < 3; j++) {
    setTimeout(function log() {
      console.log(j);
    }, j * 1000);
  }
}

b();

// Output: 0 1 2

// Explanation: let is block scoped while var is function scoped.
```

---
