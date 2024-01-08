## **Lexical Environment -**

Lexical environment is an environment where variables or functions are defined which can be specific to a function or a block. 

In javascript our lexical scope (available data + variables where the function was defined)
determines our available variables. Not where the function is called (dynamic scope)


## **Hoisting -**
Behaviour of moving variables or function declaration to the top of their respective environments during compilation phase.
Variables declared with "var" and functions are hoisted. "var" variables declared not initialised which means that initially before any value is assigned to it they are stored as undefined in memory.
But function declarations are fully hoisted but not function expressions
Hoisting happens on every execution context (For each function hoisting happens differently for the variables/functions  inside that function)

For example

console.log(sing2) //prints undefined
console.log(sing2()) // Reference Error

// function expression
var sing2 = function() {
console. log( 'uhhh la la lal)
1
// function declaration
function sing() {
console. log( 'ohhh la la lal)

sing2 is a var variable so it will be first set to undefined.


Code questions (Predict the output)

1. 
```
var one =1
var one =2;
console.log(one) // 2
```

```
2.
var one =1
console.log(one) // 1
var one =2;
```

```
3.
console.log(one) // undefined
var one =1
var one =2;
```

```
4.
a() // prints 'bye' (because functions are fully hoisted)
function a(){
console. log( 'hi' )
}
a() // prints 'bye'
function a() {
console. log( 'bye')
}
a() // prints 'bye'
```

```
5.

var favouriteFood = "grapes";

var foodThoughts = function ( ) {
console.log( "favourite food:"+ favouriteFood);
var favouriteFood = "sushi";
console.log("New favourite food: "+ favouriteFood) ;
}

foodThoughts ( )

//Output-
//undefined
//sushi
```