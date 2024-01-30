# Functions in JS

## Function Expression vs Function Declaration vs Function Statement

### Function Statement aka Function Declaration

When function is created with a name and function keyword

```jsx
function a(){
	console.log(' function statement')
}
```

### Function Expression

When function is created without a name and assigned to a variable

```jsx
var b = function(){
	console.log(' function expression b')
}

//another way of function expression
// xyz variable can only be accessed inside xyz() function
// c() should be used to call function outside
var c = function xyz(){
	console.log(' function expression c')
  console.log(xyz)
}

c() // ✅
xyz // ❌ Reference error
```

### Difference between both

```jsx
a()
b()

function a(){
	console.log(' function statement')
}
var b = function(){
	console.log(' function statement')
}

// Output
// 'function statement'
// Type Error b is not a function
```

This happens because of hoisting. Both `var` and functions are hoisted but var variables are assigned `undefined` till actual declaration, due to which this error occurs

## Anonymous function

Function without name

```jsx
function(){
	console.log('anonymous')
}
```

## First Class functions

In JavaScript, functions are first-class objects. This concept refers to the fact that functions in JavaScript are treated like any other variable.

For example, in JavaScript, functions can be assigned to variables, they can be passed as arguments to other functions, and they can be returned from other functions as well. This enables the construction of higher-order functions.

Here is an example of a function assigned to a variable:

```jsx
var x = function(a, b) {
   return a * b;
}

```

And here is an example of a function passed as an argument to another function:

```jsx
function sayHello() {
   return "Hello, ";
}
function greeting(helloMsg, name) {
   console.log(helloMsg() + name);
}
greeting(sayHello, "JavaScript!");

```

## Arrow functions

### Arrow Functions

Arrow functions are a more concise syntax for writing function expressions. They utilize a new token, `=>`, that looks like a fat arrow. Arrow functions are anonymous and change the way `this` binds in functions.

They are different from regular functions in several ways:

1. **Simpler Syntax:** Arrow functions have a shorter syntax compared to function expressions.

```jsx
const a = () => {};

```

1. **`this` Scope:** In arrow functions, `this` retains the value of the enclosing lexical context's `this`. In global code, it will be set to the global object.

```jsx
const obj = {
  id: 42,
  counter: function counter() {
    setTimeout(() => {
      console.log(this.id);
    }, 1000);
  }
};

obj.counter(); // Logs "42"

```

1. **No Arguments Object:** Arrow functions do not have their own `arguments` object. Thus, in this example, `arguments` is simply a reference to the arguments of the enclosing scope:

```jsx
var arguments = [1, 2, 3];
var arr = () => arguments[0];

arr(); // 1

```

1. **No Constructor:** Arrow functions cannot be used as constructors and will throw an error when used with new.

```jsx
var Foo = () => {};
var foo = new Foo(); // TypeError: Foo is not a constructor

```

## Higher Order functions

A higher-order function in JavaScript is a function that either accepts other functions as parameters, returns a function, or both. These functions are like any other function, but the key principle is that they manipulate other functions. 

For example, the Array method `map()` is a higher-order function as it takes a function as an argument and applies it to all elements in an array.

```jsx
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(number => number * 2);

console.log(doubled); // [2, 4, 6, 8, 10]

```

In this example, `map()` is the higher-order function and the function `number => number * 2` is the callback function passed as an argument.

## Pure & Impure functions

### Pure Functions

In JavaScript, a pure function is a function which has the following properties:

1. **Same output for the same input:** A pure function will always return the same output when provided with the same input.
2. **No Side Effects:** A pure function does not cause any observable changes outside the function itself. This means it doesn't change any external variables, doesn't read from or write to the global state, doesn't mutate any parameters, and generally doesn't interact with the outside world (like I/O operations).

Here's an example of a pure function:

```jsx
function add(a, b) {
  return a + b;
}

```

In this function, the output is always the same for any given `a` and `b`. And there are no side effects — it doesn't modify any state or variables outside the function.

### Impure Functions

On the contrary, an impure function is a function that does not have one or both of the properties of a pure function.

1. **Different output for the same input:** An impure function may return different output for the same input, often due to external factors that the function depends on.
2. **Has Side Effects:** An impure function may have side effects, such as mutating external variables, performing I/O operations, or changing the global state.

Here's an example of an impure function:

```jsx
let count = 0;

function increment() {
  count++;
}

```

In this function, the `increment` function is impure because it changes the global variable `count`. This is a side effect. Furthermore, it does not return a consistent output for the same input. In fact, it doesn't even take any input.