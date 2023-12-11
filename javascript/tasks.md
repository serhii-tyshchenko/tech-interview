**What will be the output of the following code?**
```javascript
var x = 1;
function foo() {
  x = 10;
  return;
  function x() {}
}
foo();
console.log(x); // Output: 1;
```
- ***Explanation:*** This question tests your understanding of variable hoisting and function scope. In JavaScript, variable and function declarations are hoisted to the top of their respective scopes. The function `x` is hoisted to the top of the `foo` function scope, and it becomes a local variable. The assignment `x = 10` inside the `foo` function modifies this local variable `x`, not the global one. Therefore, the output will be `1`.

**What will be the output of the following code?**
```javascript
var name = "Lokesh Prajapati";
(function() {
  console.log(name);
  var name = "Lokesh Prajapati";
})(); // Output: undefined;
```
- ***Explanation:*** This question tests your understanding of variable hoisting within functions. Even though the `name` variable is declared outside the function, the `var name` declaration inside the function is hoisted to the top of the function scope. However, the value of `name` is `undefined` at the point of the `console.log` call, because the assignment `var name = "Jane Doe"`; is not yet executed. The output will be `undefined`.

**What will be the output of the following code?**
```javascript
var x = 1;
if (function test() {}) {
  x += typeof test;
}
console.log(x); // Output: 1undefined;
```
- ***Explanation:*** This question checks your understanding of function expressions and the `typeof` operator. Although there is a function expression inside the `if` statement, it evaluates to `true`, and the block is entered. However, `f` is not defined in the outer scope because it is a function expression and not a function declaration. Therefore, typeof `f` will be `'undefined'`, and the output will be `1undefined`.

**What will be the output of the following code?**
```javascript
function sayHelloWorld() {
  return sayGoodbyWorld();
  var sayGoodbyWorld = function() {
    return "Hello, World!";
  };
  function sayGoodbyWorld() {
    return "Goodbye, World!";
  }
}
console.log(sayHelloWorld());
```
- ***Explanation:*** This question tests your understanding of function hoisting and the order of function declarations and variable declarations. The function `sayGoodbyWorld` is hoisted to the top of the `sayHelloWorldfunction` scope, and the `sayGoodbyWorld` variable declaration is also hoisted, but its assignment is not. Therefore, the first `sayGoodbyWorld` function is used, and the output will be `"Goodbye, World!"`.

**What will be the output of the following code?**
```javascript
function Parent() {}
function Child() {}
Child.prototype = new Parent();
var obj = new Child();
console.log(obj instanceof Parent); // Output: true;
```
- ***Explanation:*** This question tests your knowledge of prototypes and inheritance in JavaScript. The code creates a `Parent` and a `Child` constructor function. The `Child` prototype is set to an instance of `Parent`, creating a prototype chain. When `obj` is created using the `Child` constructor, it inherits from `Parent`. So, the output will be `true`.

**What will be the output of the following code?**
```javascript
var x = 10;
function testValue() {
  console.log(x);
  var x = 20;
}
testValue(); // Output: undefined;
```
- ***Explanation:*** This question checks your understanding of variable hoisting within functions. The var `x` declaration inside the `testValue` function is hoisted to the top of the function scope, but its assignment is not hoisted. So, at the time of `console.log`, `x` is `undefined`, and the output will be `undefined`.

**What will be the output of the following code?**
```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.greet = function() {
  return "Hello, my name is " + this.name;
};

var person1 = new Person("Lokesh Prajapati");
var person2 = new Person("Lucky");

console.log(person1.greet === person2.greet); // Output: true;
```
- *** Explanation:*** This question tests your knowledge of prototype-based inheritance and function reference equality. Both `person1` and `person2` are instances of the `Person` constructor, and they share the same greet method through the prototype chain. So, the output will be `true` because the `greet` function reference is the same for both instances.

**What will be the output of the following code?**
```javascript
console.log([] == ![]); // Output: true;
```
- ***Explanation:***This question checks your understanding of type coercion and truthy/falsy values in JavaScript. The array `[]` is truthy, and the `!` operator negates it, making it falsy. When comparing falsy and truthy values with the abstract equality (`==`) operator, both operands are converted to numbers. Falsy values are converted to `0`. So, the expression becomes `0 == 0`, and the output will be `true`.

**What will be the output of the following code?**
```javascript
function sayHi() {
  return hi;
  var hi = "Hello, World!";
}
console.log(sayHi()); // Output: undefined.
```
***Explanation:*** This question checks your understanding of variable hoisting and function return values. The var `hi` declaration is hoisted to the top of the `sayHi` function scope, but its assignment is not hoisted. At the time of the `return` statement, `hi` is undefined, and that is the value returned. The output will be `undefined`.

**What will be the output of the following code?**
```javascript
var x = 5;
function outer() {
  var x = 10;
  function inner() {
    console.log(x);
  }
  return inner;
}
var finalResult = outer();
finalResult();
```
- ***Explanation:*** This question tests your understanding of closures. The outer function creates a closure over the `x` variable, and the inner function can access it. When the inner function is called, it logs the value of the variable `x` from its closure, which is `10`. The output will be `10`.

**What will be the output of the following code?**
```javascript
function userData() {
  return userData;
}
console.log(typeof userData()); // Output: function;
```
- ***Explanation:*** This question tests your understanding of the return value of a function. The `userData` function returns itself (the function reference). Therefore, the result of calling `typeof userData()` will be `'function'`.

**What will be the output of the following code?**
```javascript
var x = 10;
function testNum() {
  console.log(x);
  if (true) {
    var x = 20;
  }
  console.log(x);
}
testNum();
```
- ***Explanation:*** This question checks your understanding of variable hoisting and variable scope within functions. Inside the `testNum` function, the var `x` declaration Inside the `if` block is hoisted to the top of the function scope but its assignment is not hoisted. So, at the first `console.log`, `x` is `undefined`. Then, `x` is assigned the value `20` within the `if` block, and at the second `console.log`, `x` will be `20`. The output will be: `20`.

**What will be the output of the following code?**
```javascript
var a = [1, 2, 3];
var b = [1, 2, 3];
console.log(a == b); // Output: false;
```
- ***Explanation:*** This question tests your understanding of array comparison in JavaScript. Although `a` and `b` contain the same values, arrays are reference types in JavaScript. When comparing two arrays using the abstract equality operator (`==`), the comparison checks whether both operands refer to the same array object in memory, which is not the case here. So, the output will be `false`.

**What will be the output of the following code?**
```javascript
var x = 5;
(function() {
  console.log(x);
  var x = 10;
})(); // Output: undefined;
```
- ***Explanation:*** This question checks your understanding of variable hoisting within functions. The var `x` declaration inside the immediately-invoked function expression (IIFE) is hoisted to the top of the function scope, but its assignment is not hoisted. So, at the time of `console.log`, `x` is `undefined`, and the output will be `undefined`.

**What will be the output of the following code?**
```javascript
function a() {
  console.log(this);
}
var b = {
  foo: a
};
b.foo(); // Output: { foo: a };
```
- ***Explanation:*** This question tests your understanding of the value of `this` in JavaScript functions. In this case, the function `a` is called as a method of the object `b`, so the value of this inside a will refer to the object `b`. The output will be the object `b` itself.

<!-- 1. Given an array of names, create an <li> with them.
2. Given an array of numbers and dates. Calculate the sum of elements greater than 150
3. Write a function that outputs the smaller of two numbers
4. Lowercase the first letter in a string
5. Calculate the sum of elements of two arrays `sumOfArrays(arr1,arr2)`. Is it possible to do it in one line?
6. Find the number of identical characters in a string (eg 'aabbaaacabdddee') and output the result as an object `{a:2, b:3}`
7. Assign to the variable week the value of the array of days of the week in Russian if `lang = 'ru'`, in English if `lang = 'en'` and `'Language not defined'` in other cases.
8. Complete task No. 7, using `switch ... case`
9. By clicking on the button with `id="btn"` add the `"input"` class to all input fields on the page;
10. `sum(5)(5) => 10`
11. Specify the reqexp that will output from +(380)66-123-45-67 38066...
12. Output a random array element.
13. List the http methods you know and explain them.
14. What do the codes mean? http 200, 404, 500
15. Display the current year.
16. Output numbers from 1 to 100 with the following condition: if the number is divisible by 3, then output `'div3'`, if by 5, then `'div5'`, if by 3 and 5, then `'div35'`
17. return x === x // false, x = ?
18. Calculate the sum of function arguments. `f() = 0`, `f(1,2,3) = 6`. -->