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
----

## Pass by value and reference
Primitive types are immutable i.e every time a new value is assigned to a variable. i.e its stored seperately in memory.
```
for example
let a = 5;
let b = a;
b++;

In this value of b changes to 6 but value of a still remains 5.
```

But for Arrays and Objects this is not the case
Arrays and Objects are passed by reference

for example
```
let obj1 = {
    a:'a',
    b:'b',
    c:'c'
}

let obj2 = obj1;

obj2.c = 'new c';

console.log(obj1) // {a:'a', b:'b', c:'new c'}
console.log(obj2) // {a:'a', b:'b', c:'new c'}
```

So both the objects are pointing to the same references in the memory and hence when the value changes it reflects in both variables.
**Similar case is for Arrays**

So if we want to copy obj1 to obj2 we can use spread operator.

```
let obj1 = {
    a:'a',
    b:'b',
    c:'c'
}

let obj2 = {...obj1};

obj2.c = 'new c';

console.log(obj1) // {a:'a', b:'b', c:'c'}
console.log(obj2) // {a:'a', b:'b', c:'new c'}
```

But this only works for first level keys and not for nested objects.

```
let obj1 = {
    a:'a',
    b:'b',
    c:{ deep1:1, deep2:2}
}

let obj2 = {...obj1};

obj2.c.deep1 = 5;

console.log(obj1)
console.log(obj2) 

Output
//obj1
{
    a: "a"​,
    b: "b",
    c:  { deep1: 5, deep2: 2 }
}
//obj2
{
    a: "a"​,
    b: "b",
    c:  { deep1: 5, deep2: 2 }
}
```

This is called as shallow copying.

To overcome this we can use 
```
obj2 = JSON.parse(JSON.stringify(obj1))
```
But this will have a lot of impact on memory if its deeply nested object.