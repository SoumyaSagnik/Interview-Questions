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

7. Given a string. The task is to check if it is Pangram or not. A pangram is a sentence containing every letter in the English Alphabet.

```javascript
const str = "A quick brown fox jumps over the lazy dog.";

function isPangram(str) {
  str = str.toLowerCase().trim();
  const chars = new Array(26).fill(false);

  for (let i = 0; i < str.length; i++) {
    if (str.charAt(i) <= "z" && str.charAt(i) >= "a")
      chars[str.charCodeAt(i) - "a".charCodeAt(0)] = true;
  }

  return chars.every((char) => char === true);
}

isPangram(str); // true
```

---

8. What is Prototype?

- In JavaScript, prototype is an object that is associated with every <a href="https://blogs-ssk.netlify.app/js-factory-constructor">constructor function</a>. Prototype is used to provide inheritance in JavaScript. The prototype object acts as a template or blueprint for creating new objects of a particular type.

```javascript
const vehicle = {
  drive: function () {
    console.log("The car is driving");
  },
};

const car = {
  make: "Honda",
};

Object.setPrototypeOf(car, vehicle);
car.drive(); // Output: The car is driving
```

- When an object is created using a constructor function, the object inherits all the properties and methods defined in the constructor's prototype. The prototype property can be used to add properties and methods to all instances of the constructor function, which can save memory and improve performance.

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }
}

Person.prototype.sayHello = function () {
  console.log("Hello from", this.name);
};

let personA = new Person("John");
personA.sayHello(); // Output: Hello from John
```

- Instead of creating the sayHello() function inside the Person class, we've created it outside and attached it to the class' prototype, so that even if thousands of Person objects are created, sayHello() function will be created only once and it'll be accessible to all the objects created through the Person's constructor function. This saves memory.

---

9. Write a program to reverse each word in a string without reversing the string.<p>Eg: John Doe &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Output: nhoJ eoD</p>

```javascript
const str = "John Doe";
function reverseWordsInString(str) {
  const words = str.split(" ");
  words.forEach((word, index) => {
    words[index] = word.split("").reverse().join("");
  });

  return words.join(" ");
}

console.log(reverseWordsInString(str));
// Output: nhoJ eoD
```

10. Predict the output.

```javascript
const a = [null, 0, 1, "0", true, false];
const b = a.filter((a) => a);
console.log(b);

// Output: [1, '0', true]
```
