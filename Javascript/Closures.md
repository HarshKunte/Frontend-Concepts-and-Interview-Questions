# Theory

When a function along with its lexical scope is returned it forms a closure.

When an outer function returns an inner function, the inner function has access to the variables of its outer function, which are not released from the memory even when the outer function is done executing itself.

Hence the inner function can be called anytime later and it will still have the access to outer function variables

So variables of outer function can act like a global variable (rather protected variable which cannot be accessed by other functions but still it's value won't be reset when the inner function is called another time) which persists in the memory for that inner function.


Advantages of Closures - 

1. Memory efficiency

For example this is a below function
```
const heavyFunction = (index) =>{

    const heavyTask = new Array(7000).fill('hello') // imagine this is a very heavy task

    console.log(heavyTask[index])
}

heavyFunction(1)
// heavyFunction(1) comes into call stack
// heavyTask array is created
// prints the item
// heavyFunction(1) is popped of the stack
// heavyTask is garbage collected

heavyFunction(2)
// heavyFunction(2) comes into call stack
// heavyTask array is created
// prints the item
// heavyFunction(2) is popped of the stack
// heavyTask is garbage collected
```

So this keeps happening again and again, which is not memory efficient.

Using closure it can be fixed like this

```
const heavyFunction = () =>{

    const heavyTask = new Array(7000).fill('hello') // imagine this is a common heavy task
    return function(index){
        console.log(heavyTask[index])
    }
}

const heavyTaskWithIndex = heavyFunction()
heavyTaskWithIndex(200)

heavyTaskWithIndex(400)

heavyTaskWithIndex(600)

//In this the heavyTask array will be created only once and will be referenced commonly for all calls.

```


# Interview Questions
Sure! Here are 20 commonly asked questions on closures in JavaScript:
## What is a closure in JavaScript?
   **Answer:** A closure is a function that has access to its own scope, the outer function's scope, and the global scope, even after the outer function has finished executing.
## How do you create a closure in JavaScript?
   **Answer:** Closures are created when a function is defined inside another function and the inner function retains access to the variables and parameters of the outer function.
## Why are closures important in JavaScript?
   **Answer:** Closures are essential for creating private variables, data encapsulation, and for maintaining state in asynchronous code.
## How do closures help with data encapsulation?
   **Answer:** Closures allow you to create private variables and functions, which are not accessible from outside the function, providing a form of data encapsulation.
## How do closures help in managing memory in JavaScript?
   **Answer:** Closures can help manage memory by allowing variables to be released when they are no longer needed, as the closure retains references to its outer function's variables. ## Can you give an example of a closure in JavaScript?
   **Answer:** Sure, here's an example:
   ```javascript
   function outerFunction() {
     const outerVariable = 'I am from the outer function';

     function innerFunction() {
       console.log(outerVariable);
     }

     return innerFunction;
   }

   const closureExample = outerFunction();
   closureExample(); // Output: "I am from the outer function"
   ```
## How can you use closures to create private variables in JavaScript?
**Answer:** By defining variables inside an outer function and returning inner functions that can access and modify those variables, you can create private variables in JavaScript.
## How does a closure maintain access to its outer function's variables even after the outer function has finished executing?
**Answer:** Closures maintain references to their outer function's variables through the scope chain, which allows them to access those variables even when the outer function has completed execution. 
## What is the relationship between closures and the garbage collector in JavaScript?
**Answer:** Closures can sometimes prevent variables from being garbage-collected when they are no longer needed, as the closure retains references to those variables.

## Can you have multiple closures in a JavaScript program?
**Answer:** Yes, you can have multiple closures in a JavaScript program, each with its own scope and access to its respective outer function's variables.

## How do you avoid memory leaks when using closures?
**Answer:** To avoid memory leaks, ensure that closures only retain references to variables that are genuinely needed and release unnecessary variables when they are no longer needed.

## What is the difference between a closure and a nested function?
**Answer:** A closure is a function that retains access to its outer function's variables, while a nested function is simply a function defined inside another function, but it does not necessarily create a closure.

## How can you use closures to implement a counter in JavaScript?
**Answer:** Closures can be used to maintain the state of a counter by returning a function that increments the counter each time it is called.

## Can you explain the "module pattern" in JavaScript and how it is implemented using closures?
**Answer:** The "module pattern" in JavaScript is a design pattern used to create private and public encapsulated modules, allowing you to organize code and hide implementation details from the outside world. It leverages closures to achieve data privacy and maintain a clean, organized code structure. By using the module pattern, you can expose only specific parts of the module that you want to be publicly accessible, while keeping the rest of the implementation hidden and protected.

Here's an example of how the module pattern is implemented using closures:

```javascript
const Module = (function() {
  // Private variables and functions
  let privateVar = 'I am private!';

  function privateFunction() {
    console.log('This is a private function.');
  }

  // Public API
  return {
    // Public variables and functions
    publicVar: 'I am public!',
    publicFunction: function() {
      console.log('This is a public function.');
    },
    getPrivateVar: function() {
      return privateVar;
    }
  };
})();

// Accessing public parts of the module
console.log(Module.publicVar); // Output: "I am public!"
Module.publicFunction(); // Output: "This is a public function."

// Attempting to access private parts of the module
console.log(Module.privateVar); // Output: undefined (Private)
Module.privateFunction(); // Output: TypeError: Module.privateFunction is not a function (Private)

// Accessing private parts using public methods
console.log(Module.getPrivateVar()); // Output: "I am private!"
```

In the example above, we create an immediately-invoked function expression (IIFE) that returns an object containing the public API of the module. The private variables and functions are defined inside the IIFE and are not directly accessible from outside the function. They are only accessible within the scope of the IIFE, creating a form of data privacy.

The public API includes the properties and methods that we want to expose to the outside world. These are accessible outside the IIFE and can be used to interact with the module. The public API can interact with the private variables and functions within the IIFE, allowing controlled access to the private data.

This way, the module pattern enables us to organize our code into self-contained, reusable units, keeping private data safe from unintended modifications or access. It is widely used in JavaScript applications to create modular and maintainable code.

## How do closures help with event handling in JavaScript?
**Answer:** Closures are often used with event handlers to maintain access to variables and data associated with the event even after the event handler function has been executed.

## What are some common use cases for closures in JavaScript?
**Answer:** Common use cases for closures include implementing private variables, creating factories, handling asynchronous operations, and implementing the module pattern.

## How do closures affect the performance of a JavaScript application?
**Answer:** While closures can be helpful in some scenarios, they can also lead to memory leaks if not used correctly, affecting performance. Properly managing closures and the data they retain is essential to avoid performance issues.

## What happens if you don't properly manage closures in JavaScript?
**Answer:** If closures are not managed correctly, they can lead to memory leaks, which may cause increased memory usage and reduced application performance.

## Can closures lead to security concerns in JavaScript applications?
**Answer:** Yes, if closures are not managed properly, they may expose sensitive data or create unintended access to private variables, potentially leading to security vulnerabilities.

## How do arrow functions in ES6 behave regarding closures compared to regular functions?
**Answer:** Arrow functions have a unique behavior regarding closures. They do not have their own `this` value and instead capture the `this` value of the surrounding context lexically, making them useful in certain closure-related scenarios.
