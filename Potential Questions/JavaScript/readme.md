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
