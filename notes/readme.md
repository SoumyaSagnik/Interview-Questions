## JavaScript

1. **JSON.parse & JSON.stringify**

- `JSON.parse()`: This method is used to parse a JSON string and convert it into a JavaScript object.

```javascript
const jsonString = '{"name": "John", "age": 27}';
const obj = JSON.parse(jsonString);
console.log(obj.name); // John
```

- `JSON.stringify()`: This method is used to convert a JavaScript object into a JSON string.

```javascript
const obj = { name: 'John', age: 27 };
const jsonString = JSON.stringify(obj);
console.log(jsonString); // {"name":"John","age":27}
```
