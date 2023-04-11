1. What is a closure? Where have you implemented them?

- A function along with its lexical environment is known as closure. When a function is returned from another function, the returned function has access to the variables declared in the function from where it was returned. This is the underlying concept of closures. <a href="https://blogs-ssk.netlify.app/js-closures">More..</a>

- I have implemented closures while using the useState hook in react. Under the hood, the useState hook uses closure to create a 'private' state variable that is accessible only to the component where it is defined.

---

2. Create your own implementation of stack.

```javascript
class Stack {
  constructor() {
    this.items = [];
  }

  push(element) {
    this.items.push(element);
  }

  pop() {
    if (this.isEmpty()) return "Underflow";
    return this.items.pop();
  }

  peek() {
    if (this.isEmpty()) return "No items in stack";
    return this.items[this.items.length - 1];
  }

  isEmpty() {
    return this.items.length === 0;
  }

  printStack() {
    let str = "";
    for (let i = 0; i < this.items.length; i++) {
      str += this.items[i] + " ";
    }
    return str.trim();
  }
}
```

3. Provide output for the code snippets

```javascript
var a = 10;
function b() {
  var a;
  console.log(a);
  a = 20;
}

b();

// Output: undefined
```

Reason: hoisting inside function b().

```javascript
var a = 10;
function b() {
  console.log(a);
  a = 20;
}

b();

// Output: 10
```

Reason: Scope chain.

---

4. Given a file name. Change its extension based on the following rules:

- .txt -> .doc
- .doc, .html -> .pdf
- no extension -> .txt

Examples:

- `test.txt.doc -> test.txt.pdf`
- `test -> test.txt`

```javascript
function extensionConversion(str) {
  const wordArray = str.split(".");

  // if there's no extension
  if (wordArray.length === 1) return str + ".txt";

  const extension = wordArray[wordArray.length - 1];

  // html
  if (extension.length === 4) {
    wordArray[wordArray.length - 1] = "pdf";
    return wordArray.join(".");
  } else {
    // !html
    switch (extension) {
      case "txt":
        wordArray[wordArray.length - 1] = "doc";
        return wordArray.join(".");
      case "doc":
        wordArray[wordArray.length - 1] = "pdf";
        return wordArray.join(".");
    }
  }
}

console.log(extensionConversion("test.txt"));
console.log(extensionConversion("test2"));
console.log(extensionConversion("test3.doc"));
console.log(extensionConversion("test4.txt.doc"));
console.log(extensionConversion("test5.txt.html"));
console.log(extensionConversion("test6.doc.doc"));
```

Output:
`test.doc`
`test2.txt`
`test3.pdf`
`test4.txt.pdf`
`test5.txt.pdf`
`test6.doc.pdf`

---

5. Write a program to conver 24 hour time to 12 hour time. <p>Example: 00:00 -> 12:00 AM &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 18:45 -> 06:45 PM</p>

```javascript
function toTwelveHHourFormat(time) {
  const [hour, min] = time.split(":");

  let newHour = parseInt(hour);

  const suffix = newHour < 12 ? "AM" : "PM";

  newHour = newHour % 12 || 12;

  return `${newHour.toString().padStart(2, "0")}:${min} ${suffix}`;
}

console.log(toTwelveHHourFormat("18:25"));
console.log(toTwelveHHourFormat("00:00"));
console.log(toTwelveHHourFormat("12:00"));
console.log(toTwelveHHourFormat("09:59"));
```

Output: `06:25 PM` `12:00 AM` `12:00 PM` `09:59 AM`

---

6. Predict the output of the following code.

```javascript
const shape = {
  radius: 10,
  diameter() {
    return this.radius * 2;
  },
  perimeter: () => 2 * Math.PI * this.radius,
};

console.log(shape.diameter()); // 20
console.log(shape.perimeter()); // NaN
```

Since there's no `this` keyword for arrow function.

---

7. What is the difference between async/await and promises in JavaScript? When would you use one over the other, and how do you handle errors with async/await and promises?

- async/await is a newer feature that was introduced in ES2017, while promises were introduced in ES6.
- Async/await is built on top of promises and provides a more concise syntax for working with asynchronous code.
- Promises are objects that represent a value that may not be available yet, but will be resolved at some point in the future. Promises have a `then` method that can be used to handle the resolved value and a `cathc` method that can be used to handle the error.
- Async/await allows us to write asynchronous code in a way that looks like synchronous code, which can be easier to read and understand. Withh async/await we use the `await` keyword to pause the execution of the function until the promise is resolved or rejected.

<p>When to use what:</p>

- Promises are more appropriate in cases where you need to perform `several` asynchronous operations in parallel. This is because promises can be chained together using the `then()` method, which allows you to execute several asynchronous operations concurrently.
- Async/await is more appropriate in cases where you need to perform a `sequence` of asynchronous operations . This is because async/await provides a more synchronous way of writing asynchronous code.
- Promises are more appropriate in cases where you need to handle errors in a more fine-grained way. This is because promises allow you to handle errors on a per-operation basis using the `catch()` method.
- Async/await is more appropriate in cases where you need to handle errors in a more centralized way. This is because you can use a single `try/catch` block around the entire sequence of asynchronous operations.

<p> In terms of handling errors:

- Both async/await and promises allow you to handle errors using the `try/catch` block. With promises, you can use the `catch()` method to catch errors. With async/await, you can use the `try/catch` block around the `await` expression to catch errors.

---
