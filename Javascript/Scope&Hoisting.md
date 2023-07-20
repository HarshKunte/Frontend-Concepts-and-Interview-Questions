Scopes and Hoisting
- [Theory](#theory)
- [Scope](#scope)
  - [**Lexical scope and scope chaining -**](#lexical-scope-and-scope-chaining--)
  - [**Function scope and Block scope**](#function-scope-and-block-scope)
  - [**Hoisting**](#hoisting)
  - [**Temporal Dead Zone**](#temporal-dead-zone)
- [Interview Questions](#interview-questions)
  - [What is the difference between global scope and local scope in JavaScript?](#what-is-the-difference-between-global-scope-and-local-scope-in-javascript)
  - [What is lexical scope in JavaScript?](#what-is-lexical-scope-in-javascript)
  - [What is hoisting in JavaScript? Explain with an example.](#what-is-hoisting-in-javascript-explain-with-an-example)
  - [Can you hoist variable declarations and function declarations differently? Explain.](#can-you-hoist-variable-declarations-and-function-declarations-differently-explain)
  - [What is the difference between var, let, and const regarding hoisting and scope?](#what-is-the-difference-between-var-let-and-const-regarding-hoisting-and-scope)
  - [How does JavaScript handle variables declared without var, let, or const?](#how-does-javascript-handle-variables-declared-without-var-let-or-const)
  - [What is the difference between var and let in terms of block scoping?](#what-is-the-difference-between-var-and-let-in-terms-of-block-scoping)
  - [What is the Temporal Dead Zone (TDZ) in JavaScript?](#what-is-the-temporal-dead-zone-tdz-in-javascript)
  - [What happens when you declare a variable with the same name in both the local and global scope?](#what-happens-when-you-declare-a-variable-with-the-same-name-in-both-the-local-and-global-scope)
  - [Explain the "this" keyword in JavaScript and how its value is determined within different scopes.](#explain-the-this-keyword-in-javascript-and-how-its-value-is-determined-within-different-scopes)
- [Tricky Questions](#tricky-questions)
- [Coding Questions](#coding-questions)

## Theory

## Scope

Scope defines the area of visibility of variables and functions. If a variable or function can be accessed or not is decided by their scope.

### **Lexical scope and scope chaining -**

Lexical scope is the scope of a variable or function based on where it is defined in the source code. Lexical scope is ability of child function able to access the scope of parent function. An items lexical scope is the area where it got defined(static scope) and not where its getting called(dynamic scope).

```
var x = 1;

function a(){
	var x = 2;
	function b(){
		console.log(x);
	}
}
a();
// output => 2

```

Scope chain means child function has access to all the variables available in scope parent variable and hence in similar the scope of parent gets chained with its own parent and so child also has access to grand parents scope. So if the child cannot find a variable in parents scope it will look into grand parents scope....this can go digging till it reaches the Global scope.

### **Function scope and Block scope**

function scope- By default JS is function scoped. Function scope the variable declared inside function cannot be accessed outside function.

block scope - Block means '{}'. variables decalred inside this block cannot be accessed outside block. Let and const variables are block scoped. For example if a let variable is defined inside if block or for loop it will be only accessible inside those blocks. But variables decalred using 'var' can be outside of the block too as they are function scoped.

### **Hoisting**

Hoisting is a javascript mechanism, where variables and function declarations are moved to the top their respective environment during compilation. 

Variables declared with ******var******  and functions are hoisted.

Variables declared with `var` are initially stored as undefined in memory, until a value is assigned to it. But functions are fully stored inside the memory.

Because of hoisting we can access `var`  variables and functions before they are declared in the source code. Only the difference is that until the value is assigned to the variable in the source code `var` variables will be stored as **undefined**, but functions are fully stored hence can be executed.

### **Temporal Dead Zone**
The Temporal Dead Zone (TDZ) is a behavior in JavaScript that occurs when trying to access a variable declared with `let` or `const` before its actual declaration. During the TDZ, the variable exists but is not yet initialized and cannot be accessed. This concept is a result of the block scoping introduced with ES6 (ECMAScript 2015) for variables declared using `let` and `const`.

In the TDZ, any attempt to access the variable before its declaration results in a `ReferenceError`, signaling that the variable is not yet defined.

Here's an example to illustrate the Temporal Dead Zone:

```javascript
console.log(myVar); // Error: Cannot access 'myVar' before initialization
let myVar = 10;
```

In the example above, we try to access the variable `myVar` before its actual declaration. This results in a `ReferenceError`, indicating that the variable is in the Temporal Dead Zone.

The TDZ exists from the start of the current block (e.g., function, loop, or any pair of curly braces `{}`) until the point of actual declaration. The variable becomes accessible only after the declaration is processed by the JavaScript engine.

## Interview Questions

### What is the difference between global scope and local scope in JavaScript?

1. **Global Scope:**
   - Variables or functions declared outside of any function or block have a global scope.
   - Variables in the global scope are accessible from any part of the code, including inside functions and blocks.
   - When a variable is declared in the global scope, it becomes a property of the global object (in browsers, the global object is `window`).
   - Global variables can lead to potential naming conflicts and are generally discouraged in larger applications to avoid unintended interactions between different parts of the code.

   Example of a global variable:
   ```javascript
   const globalVar = 'I am a global variable';
   function globalFunction() {
     console.log('I am a global function');
   }
   ```

2. **Local Scope:**
   - Variables declared inside a function or block have a local scope, also known as function scope (for variables declared with `var`) or block scope (for variables declared with `let` or `const`).
   - Local variables are only accessible within the function or block where they are declared.
   - Local variables take precedence over global variables with the same name. If a local variable shares the same name as a global variable, the local variable will be used within the scope of the function or block.

   Example of a local variable:
   ```javascript
   function localFunction() {
     const localVar = 'I am a local variable';
     console.log(localVar);
   }
   ```

   In the above example, `localVar` is a local variable and can only be accessed within the `localFunction`. It does not interfere with any variable of the same name declared in the global scope.


### What is lexical scope in JavaScript?
Refer Theory section.
### What is hoisting in JavaScript? Explain with an example.
Refer Theory section.

### Can you hoist variable declarations and function declarations differently? Explain.

Yes, variable declarations and function declarations are hoisted differently in JavaScript. Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the code is executed. However, there are some differences in how variables and functions are hoisted:

1. **Variable Declarations (var):**
   - Variables declared using `var` are hoisted and initialized with `undefined` at the top of their scope. However, the assignment (value assignment) is not hoisted.
   - This means you can access the variable before its actual declaration in the code, but the value will be `undefined` until the variable is assigned a value later in the code.

   Example of variable hoisting:
   ```javascript
   console.log(myVar); // Output: undefined
   var myVar = 10;
   console.log(myVar); // Output: 10
   ```

   In the example above, `myVar` is hoisted to the top of its scope, but its value is `undefined` until the line where it's assigned the value `10`.

2. **Function Declarations:**
   - Function declarations are fully hoisted, which means both the function name and its implementation are hoisted to the top of their scope.
   - Unlike variables, you can call the function before its actual declaration in the code.

   Example of function hoisting:
   ```javascript
   sayHello(); // Output: Hello!
   function sayHello() {
     console.log('Hello!');
   }
   ```

   In the example above, the function `sayHello` is hoisted to the top of its scope, allowing us to call it before its actual declaration in the code.

It's important to note that function expressions (functions assigned to variables) do not behave the same way as function declarations. Function expressions are not hoisted like function declarations, so you cannot call them before their declaration.

Example of function expression (not hoisted):
```javascript
sayHello(); // Error: sayHello is not a function

const sayHello = function() {
  console.log('Hello!');
};
```

To avoid potential issues with hoisting and ensure better code readability, it is recommended to declare variables and functions before their usage in the code, regardless of hoisting behavior.

### What is the difference between var, let, and const regarding hoisting and scope?

The main differences between `var`, `let`, and `const` regarding hoisting and scope are as follows:

1. **Hoisting:**
   - `var`: Variables declared with `var` are hoisted to the top of their scope and are initialized with `undefined`. However, the assignment (value) of the variable is not hoisted.
   - `let` and `const`: Variables declared with `let` and `const` are hoisted to the top of their scope but are not initialized. This means that accessing the variable before its declaration (temporal dead zone) will result in a ReferenceError.

2. **Scope:**
   - `var`: Variables declared with `var` have function scope or global scope, depending on whether they are declared inside a function or outside any function (in the global scope).
   - `let` and `const`: Variables declared with `let` and `const` have block scope. They are only accessible within the block where they are declared, such as inside a loop, if statement, or any curly braces `{}`.

3. **Redeclaration:**
   - `var`: Variables declared with `var` can be redeclared in the same scope without any errors. The later declaration will overwrite the earlier one.
   - `let` and `const`: Variables declared with `let` and `const` cannot be redeclared in the same scope. Attempting to do so will result in a SyntaxError.

4. **Reassignment:**
   - `var` and `let`: Variables declared with `var` or `let` can be reassigned with new values.
   - `const`: Variables declared with `const` cannot be reassigned after declaration. They are read-only constants.

Examples:

```javascript
// Example with var
console.log(a); // Output: undefined
var a = 10;
console.log(a); // Output: 10

// Example with let and const
console.log(b); // Error: Cannot access 'b' before initialization
let b = 20;

const c = 30;
c = 40; // Error: Assignment to constant variable

// Example with scope
function exampleFunction() {
  var functionVar = 'I have function scope';
  let blockLet = 'I have block scope';
  const blockConst = 'I also have block scope';
}

console.log(functionVar); // Error: functionVar is not defined
console.log(blockLet); // Error: blockLet is not defined
console.log(blockConst); // Error: blockConst is not defined
```

### How does JavaScript handle variables declared without var, let, or const?

In JavaScript, when you declare a variable without using var, let, or const, the variable is automatically assigned to the global object in non-strict mode. In a browser environment, the global object is usually the window object, while in Node.js, it is the global object.

```
function exampleFunction() {
  undeclaredVar = 10; // Declaration without var, let, or const
  console.log(undeclaredVar); // Output: 10
}

exampleFunction();
console.log(undeclaredVar); // Output: 10 (Accessed from the global scope)
```

### What is the difference between var and let in terms of block scoping?

**Block Scoping:**
1. **var:**
   - Variables declared with `var` have function scope or global scope, but they do not have block scope.
   - When you declare a variable with `var` inside a block (e.g., inside an `if`, `for`, or any curly braces `{}`), the variable is accessible throughout the entire function where the block is present.
   - If a variable is declared with `var` inside a block, it is hoisted to the top of the function and can be accessed even before its actual declaration.

   Example of `var` with block scope behavior:
   ```javascript
   function exampleFunction() {
     if (true) {
       var blockVar = 'I am declared with var';
       console.log(blockVar); // Output: 'I am declared with var'
     }

     console.log(blockVar); // Output: 'I am declared with var'
   }
   ```
   In the example above, `blockVar` is declared with `var` inside the `if` block. Despite the block being present, `blockVar` is accessible outside the block, indicating it does not have block scope.

2. **let:**
   - Variables declared with `let` have block scope, which means they are accessible only within the block where they are declared, such as inside an `if`, `for`, or any curly braces `{}`.
   - Variables declared with `let` are not hoisted to the top of the block. Instead, they remain within the scope where they were declared.

   Example of `let` with block scope behavior:
   ```javascript
   function exampleFunction() {
     if (true) {
       let blockLet = 'I am declared with let';
       console.log(blockLet); // Output: 'I am declared with let'
     }

     // console.log(blockLet); // Error: blockLet is not defined (outside the block)
   }
   ```
   In the example above, `blockLet` is declared with `let` inside the `if` block. The variable `blockLet` is only accessible within that block and will result in an error if accessed outside the block.

### What is the Temporal Dead Zone (TDZ) in JavaScript?

Refer Theory section.

### What happens when you declare a variable with the same name in both the local and global scope?

When you declare a variable with the same name in both the local (function) scope and the global scope, the local variable takes precedence over the global variable within the scope where it is declared. This behavior is referred to as "variable shadowing."

In other words, the local variable with the same name "shadows" the global variable, and any reference to that variable within the local scope will refer to the local variable, not the global one. However, the global variable remains unchanged and is still accessible outside the local scope.

```
const globalVar = 'I am a global variable';

function exampleFunction() {
  const globalVar = 'I am a local variable';
  console.log(globalVar); // Output: 'I am a local variable'
}

exampleFunction();
console.log(globalVar); // Output: 'I am a global variable'
```

### Explain the "this" keyword in JavaScript and how its value is determined within different scopes.

In JavaScript, the `this` keyword refers to the current execution context, representing the object that the function or method is called on. The value of `this` is determined dynamically based on how a function is invoked, and it can behave differently within different scopes. The behavior of `this` can be a common source of confusion for developers, so understanding how it works is essential.

The value of `this` is primarily determined by the way a function is called, and it can have one of the following values:

1. **Global Context (Default):**
   When a function is called in the global scope (i.e., not called on an object), `this` points to the global object. In browsers, the global object is `window`, while in Node.js, it is `global`.

   Example of `this` in the global context:
   ```javascript
   console.log(this); // In a browser: Output: Window, In Node.js: Output: [object Object]
   function globalFunction() {
     console.log(this); // In a browser: Output: Window, In Node.js: Output: [object Object]
   }
   globalFunction();
   ```

2. **Function Invocation:**
   When a function is called as a standalone function (not as a method on an object), `this` still points to the global object. This is true for functions defined using the `function` keyword.

   Example of `this` in function invocation:
   ```javascript
   function standaloneFunction() {
     console.log(this); // In a browser: Output: Window, In Node.js: Output: [object Object]
   }
   standaloneFunction();
   ```

3. **Method Invocation:**
   When a function is called as a method on an object, `this` points to the object that owns the method. The object to the left of the dot when the method is called becomes the `this` context.

   Example of `this` in method invocation:
   ```javascript
   const obj = {
     name: 'John',
     greet: function() {
       console.log(this.name);
     }
   };
   obj.greet(); // Output: 'John'
   ```

4. **Constructor Invocation:**
   When a function is called using the `new` keyword to create an instance of an object, `this` points to the newly created object.

   Example of `this` in constructor invocation:
   ```javascript
   function Person(name) {
     this.name = name;
   }
   const john = new Person('John');
   console.log(john.name); // Output: 'John'
   ```

5. **Explicit Binding:**
   You can explicitly set the value of `this` using methods like `call()`, `apply()`, or `bind()` on a function.

   Example of explicit binding using `call()`:
   ```javascript
   function sayHello() {
     console.log(`Hello, ${this.name}`);
   }
   const person = { name: 'John' };
   sayHello.call(person); // Output: 'Hello, John'
   ```


## Tricky Questions

1. **Question:** What will be the output of the following code?
    
    ```jsx
    var x = 10;
    function foo() {
      console.log(x);
      var x = 20;
    }
    foo();
    
    ```
    
    **Answer:** The output will be `undefined`. Even though `x` is declared in the global scope, the local variable `x` inside the `foo()` function is hoisted, and its value is `undefined` when the `console.log()` statement is executed.
    
2. **Question:** What will be the output of the following code?
    
    ```jsx
    var x = 10;
    function bar() {
      console.log(x);
    }
    function foo() {
      var x = 20;
      bar();
    }
    foo();
    
    ```
    
    **Answer:** The output will be `10`. The `bar()` function is called from within the `foo()` function, but since there is no local `x` variable declared inside `foo()`, it looks for `x` in the outer scope, which is the global scope.
    
3. **Question:** How can you create a private variable in JavaScript using closures?
**Answer:** You can create a private variable by defining a function inside another function and referencing the outer function's variables inside the inner function. The inner function forms a closure, giving it access to the outer function's variables even after the outer function has finished executing.
4. **Question:** What will be the output of the following code?
    
    ```jsx
    var x = 10;
    function foo() {
      console.log(x);
      x = 20;
    }
    foo();
    console.log(x);
    
    ```
    
    **Answer:** The output will be:
    
    ```
    10
    20
    
    ```
    
    The `foo()` function logs the global `x`, which is `10`, and then updates the global `x` to `20`. The second `console.log()` statement logs the updated global `x`.


## Coding Questions

```jsx
var x = 10;

function bar() {
  console.log(x);
}

function foo() {
  var x = 20;
  bar();
}

foo();

//Output
//10
```

```jsx
function outer() {
  var x = 10;

  function inner() {
    console.log(x);
  }

  x = 20;
  inner();
}

outer();

//Output
//20
```

```jsx
var x = 10;

function foo() {
  console.log(x);
}

function bar() {
  var x = 20;
  return foo;
}

var baz = bar();
baz();

//Output
//10
```

```jsx
function foo() {
  console.log(x);
}

function bar() {
  var x = 20;
  foo();
}

var x = 10;
bar();

//Output
//10
```

```jsx
function outer() {
  function inner() {
    console.log(x);
  }

  var x = 10;
  return inner;
}

var x = 20;
var foo = outer();
foo();

//Output
//10
```