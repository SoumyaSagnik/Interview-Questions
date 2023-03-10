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
