## 🔸 **Hoisting**

Covers **variable hoisting**, **function hoisting**, **TDZ**, **output predictions**, and **code-based questions**. Aimed at fresher to mid-level roles.

---

### ✅ **Single-Line / Theory Questions**

1. What is hoisting in JavaScript?
2. Which declarations are hoisted — `var`, `let`, `const`, functions?
3. What does "initialized as `undefined`" mean in hoisting?
4. Is the value hoisted along with the variable?
5. What is the Temporal Dead Zone (TDZ)?
6. Do `let` and `const` get hoisted?
7. How is function declaration hoisting different from function expression hoisting?
8. Does arrow function behave like a declaration or expression?
9. What will happen if you access a `let` variable before it’s declared?
10. Are classes hoisted?
11. Why is hoisting considered useful? And when can it be dangerous?
12. Can you hoist variables from inside a block `{}` to outside?
13. Is function hoisting block scoped?
14. What’s the difference between hoisting and scope?
15. Does JavaScript interpreter allocate memory before code runs?

---

### ✅ **Guess the Output**

16.

```js
console.log(a);
var a = 10;
```

> `undefined`

---

17.

```js
console.log(b);
let b = 20;
```

> ❌ `ReferenceError: Cannot access 'b' before initialization`

---

18.

```js
greet();
function greet() {
  console.log("Hello!");
}
```

> `Hello!`

---

19.

```js
hello();
var hello = function () {
  console.log("Hi");
};
```

> ❌ `TypeError: hello is not a function`

---

20.

```js
sayHi();
let sayHi = function () {
  console.log("Hi");
};
```

> ❌ `ReferenceError`

---

21.

```js
console.log(typeof someVar);
var someVar = "value";
```

> `'undefined'`

---

22.

```js
function outer() {
  console.log(x);
  var x = 5;
}
outer();
```

> `undefined`

---

23.

```js
function test() {
  console.log(a);
  if (false) {
    var a = 50;
  }
}
test();
```

> `undefined` — due to hoisting inside the function

---

24.

```js
{
  console.log(foo);
  var foo = "bar";
}
```

> `undefined`

---

25.

```js
{
  console.log(foo);
  let foo = "bar";
}
```

> ❌ `ReferenceError` (TDZ for `let`)

---

26.

```js
class Car {}
const c = new Car();
```

> ✅ Works fine — class declarations are hoisted but not initialized

---

27.

```js
new Vehicle();
class Vehicle {}
```

> ❌ `ReferenceError: Cannot access 'Vehicle' before initialization`

---

### ✅ **Code Snippets / Practice**

28. Hoisting `var` vs `let`:

```js
function demo() {
  console.log(name1); // ?
  console.log(name2); // ?
  var name1 = "Alice";
  let name2 = "Bob";
}
demo();
```

---

29. Function hoisting:

```js
run();
function run() {
  console.log("Running");
}
```

---

30. Function expression not hoisted:

```js
run();
var run = function () {
  console.log("Running");
};
```

---

31. Hoisting in nested scope:

```js
var x = 1;
function test() {
  console.log(x); // ?
  var x = 2;
}
test();
```

---

32. TDZ example:

```js
function test() {
  console.log(a); // ReferenceError
  let a = 5;
}
test();
```

---

33. Arrow function not hoisted:

```js
sayHi();
var sayHi = () => console.log("Hi");
```

---

34. Hoisting in `for` loop:

```js
for (var i = 0; i < 1; i++) {
  console.log(i);
}
console.log(i); // ?
```

> `1`

---

35. Function declaration inside block:

```js
{
  function sayHello() {
    console.log("Hello");
  }
}
sayHello(); // May throw error depending on mode
```

---

36. Class hoisting issue:

```js
const user = new Person(); // Error
class Person {}
```

---

37. Double declaration with `var`:

```js
var x = 10;
var x = 20;
console.log(x); // 20
```

---

38. Shadowing with `let` inside block:

```js
var x = 10;
{
  let x = 20;
  console.log(x); // 20
}
console.log(x); // 10
```

---

39. Hoisting doesn’t mean value is moved:

```js
console.log(greet); // undefined
var greet = "hello";
```

---

40. Function vs block hoisting:

```js
if (true) {
  function f() {}
}
f(); // Error in strict mode
```

---
