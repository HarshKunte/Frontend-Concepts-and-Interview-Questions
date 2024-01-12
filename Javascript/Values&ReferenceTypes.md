# Values and Reference Types


In JavaScript, data types can be broadly categorized into two main groups: primitive types and reference types. Understanding the differences between these two types is crucial for writing efficient and bug-free JavaScript code.

### 1. **Primitive Types:**

Primitive types in JavaScript are simple, immutable data types. There are six primitive data types in JavaScript:

- **String:** Represents a sequence of characters.
- **Number:** Represents numeric values.
- **Boolean:** Represents either `true` or `false`.
- **Undefined:** Represents an uninitialized variable.
- **Null:** Represents the intentional absence of any object value.
- **Symbol:** Introduced in ECMAScript 6, represents a unique identifier.

Primitive types are stored directly in the variable's location, and when you assign one variable to another, you are copying the actual value.

Example:

```jsx
let a = 5;
let b = a; // 'b' now has a copy of the value of 'a'
a = 10;
console.log(b); // Outputs 5, because 'b' is a copy of the original value of 'a'

```

### 2. **Reference Types:**

Reference types, on the other hand, are more complex. They include objects, arrays, functions, etc. Unlike primitive types, variables that hold reference types don't actually contain the data but instead, they store a reference to the memory location where the data is stored.

Example:

```jsx
let obj1 = { name: 'John' };
let obj2 = obj1; // 'obj2' now references the same object as 'obj1'
obj1.name = 'Jane';
console.log(obj2.name); // Outputs 'Jane', because 'obj2' references the same object as 'obj1'

```

### Tricky Concepts:

### a. **Passing by Value vs. Passing by Reference:**

- Primitive types are passed by value. When you pass a primitive type to a function, a copy of the value is passed.
- Reference types are passed by reference. When you pass a reference type to a function, you're passing the reference to the object, not a copy of the object.

Example:

```jsx
function modifyPrimitive(x) {
  x = 10;
}

function modifyObject(obj) {
  obj.name = 'Updated';
}

let num = 5;
modifyPrimitive(num);
console.log(num); // Outputs 5, because 'num' is a primitive and is passed by value

let person = { name: 'John' };
modifyObject(person);
console.log(person.name); // Outputs 'Updated', because 'person' is an object and is passed by reference

```

### b. **Immutability:**

- Primitive types are immutable. Once a primitive value is assigned, it cannot be changed.
- Reference types, like objects, are mutable. You can modify the properties of an object even after it has been created.

Example:

```jsx
let str = 'Hello';
str[0] = 'W'; // This won't change the value of 'str'
console.log(str); // Outputs 'Hello'

let arr = [1, 2, 3];
arr.push(4); // This changes the array
console.log(arr); // Outputs [1, 2, 3, 4]

```

Understanding these concepts is crucial for avoiding common pitfalls and writing more predictable and maintainable JavaScript code.

### Copying a primitive:

`var a = 13         // assign `13` to `a`
var b = a          // copy the value of `a` to `b`
b = 37             // assign `37` to `b`
console.log(a)     // => 13`

The original was not changed, we can only change the copy.

### 

### Copying a reference:

`var a = { c: 13 }  // assign the reference of a new object to `a`
var b = a          // copy the reference of the object inside `a` to new variable `b`
b.c = 37           // modify the contents of the object `b` refers to
console.log(a)     // => { c: 37 }`

The original was also changed, since the reference got copied.