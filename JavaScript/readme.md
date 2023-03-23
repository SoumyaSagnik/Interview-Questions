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
