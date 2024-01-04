# What is a variable in javascript?

A variable is a container for a value, like a number we might use in a sum, or a string that we might use as part of a sentence.

# **How to create a variable?**

In JS variables can be created using 3 keywords

- var
- let
- const

Using `var` and `let` values can be reassigned

Using `const` values cannot be reassigned.

Example -

`let language = “Javascript”`

let - keyword

language - variable name

= - operator which tells that value is assigned

“Javascript” - value

# Variable naming.

Variable names are case sensitive in JS

There are certain rules for how to name your variables in JS.

let counter ✅

let resetCounter ✅ (camel Case - Best Practice)

let resetCounterBy5✅  (alphabets and digits allowed)

let $counter✅  (Starting with $ is allowed)

let _counter✅  ( _ is allowed not recommended)

let  15days ❌ (starting with digits is not allowed)

let  reset-counter ❌ (no special characters between excluding ‘_ and $’)

let function ❌ (no usage of keywords as variable names)

Also important thing is to keep variable names intuitive and meaningful

# Global and Local variables

### Global variables -

Variables declared outside of any function is treated as global variable.

It can be accessed within any function as its global

```jsx
let globalVar = 5;
function print(){
	console.log(globalVar)
}
```

### Local variables -

Variables declared inside a specific function are treated as local variables.

Local variables cannot be accessed outside of function it is declared in. 

```jsx
let globalVar = 5;
function print(){
	let localVar = 10;
	console.log(globalVar) //5
  console.log(localVar) //10
}

console.log(globalVar) //5
console.log(localVar) // Reference error
```

### Variables declared without using any keyword

Variables can also be declared without using any keyword and it works! 

These variables are treated like Global variables and can be accessed anywhere in the code even if they are declared inside of any function.

! BUT DECLARING VARIABLE LIKE THIS IS NOT RECOMMENDED !

```jsx

function print(){
	let localVar = 10;
  globalVarWithoutKeyword = 50 
	console.log(globalVarWithoutKeyword ) //50
  console.log(localVar) //10
}
print()
console.log(globalVarWithoutKeyword ) //50
console.log(localVar) // Reference error
```

However, if we add `'use strict'` to enter strict mode, such declaration method is prohibited