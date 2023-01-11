## Types in JS

Primitive
1. number
    - 5
2. string
    - 'hello world '
3. boolean
    - true/false
4. undefined
    - It is absence of definition
5. null
    - It is absence of value
6. Symbol ----- (introduced in ES6)
    - Symbol('just me')

Non Primitive
1. Array
2. Objects
3. Function


**Important points**

- typeof undefined = undefined
- tyopeof null = Object
- typeof Symbol = symbol
- typeof [] (this is an Array) = object
- typeof {} = object
- typeof function() {} = function

Arrays and Functions are objects in JS.

for ex -
let a = function(){
    return 5
}
a.hi = "hi"

So in this way properties can be added to function similar to objects.

As typeof [] is an object there is a way to check where a variable is an array or object

```
let a = [1,2,3,4]
Array.isArray(a) //true

let a = {1,2,3,4}
Array.isArray(a) //false
```