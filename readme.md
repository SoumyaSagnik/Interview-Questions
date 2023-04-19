# Interview Questions

`HTML` `CSS` `JavaScript` `React`

1. What is div vs span or block vs inline?

- `Block-level Elements`: A block level element always starts on a new line, and the browsers automatically add some space (margin) before and after the element. A block level element always takes up the full width available (100% of parent). Eg: div, p.

- `Inline Elements`: An inline element does not start on a new line. It takes up minimum space i.e., as much width as necessary. Eg: span

- The `div` element is block level and is often used as a container for other HTML elements.

- The `span` element is an inline container used to mark up a part of text, or document.

- Another important point to note is that an inline element cannot contain a block level element. Block elements can contain inline elements.

- However there are some exceptions to the above rule. Eg, the `a` tag, which is an inline element, can contain block level elements such as `div` or `p` if they are used within the `a` tag as an alternative to `href` attribute. This is known as the `block link` pattern.

- But in general, it is best practice to avoid nesting block level elements inside inline elements to ensure proper HTML structure and to avoid unexpected layout issues.

---

2. What is inline-block? Difference between block, inline-block, and inline.

- The three most common values for `display` property are: `block`, `inline-block`, and `inline`.

- `display: block`: Take up the entire space (width: 100%) of the parent by default. We can specify height and width to these elements. These elements always start in a new line. We can apply top and bottom margins.

- `display: inline-block`: Elements don't start in a new line. Their heights and widths can be specified. By default take take minimum space. We can apply top and bottom margins.

- `display: inline`: They don't start in a new line, take minimum space and we cannot apply height and width properties to them. Margin top and bottom doesn't work here.

---

3. What is SCSS? How is it different from CSS? How does it get transpired to CSS?

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

4. What are positions in CSS? Differentiate between them.

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

5. Explain CSS Specificity.

- In CSS, specificity is the measure of how specific a selector is in selecting an element or group of elements on a web page. Specificity is determined by the number and type of selectors used in the CSS rule, `and it determines which CSS rule is applied to an element when multiple rules target the same element`.

- Each `id` selector increases the specificity by `100`. Each `class/ attribute/ pseudo class` selector increases specificity by `10`. Each `tag/ element` selector increases the specificity by `1`. CSS rule having the highest specificity is applied to the concerned element.

- Precedence order: !important > inline-css > id > class > tag.

---

6. What is the difference between Reset CSS and Normalize CSS?

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

7. Differentiate between let, var, and const.

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
