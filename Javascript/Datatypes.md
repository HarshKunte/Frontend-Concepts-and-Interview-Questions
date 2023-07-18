
- [Theory](#theory)
- [Interview Questions](#interview-questions)
  - [What are the primitive data types in JavaScript?](#what-are-the-primitive-data-types-in-javascript)
  - [What is the difference between null and undefined in JavaScript?](#what-is-the-difference-between-null-and-undefined-in-javascript)
  - [What is NaN in JavaScript? How is it different from undefined?](#what-is-nan-in-javascript-how-is-it-different-from-undefined)
  - [What is the difference between == and === in JavaScript?](#what-is-the-difference-between--and--in-javascript)
  - [What is type coercion in JavaScript?](#what-is-type-coercion-in-javascript)
  - [How do you create a new object in JavaScript?](#how-do-you-create-a-new-object-in-javascript)
  - [What is the difference between truthy and falsy values in JavaScript?](#what-is-the-difference-between-truthy-and-falsy-values-in-javascript)
  - [What is the difference between pass-by-value and pass-by-reference in JavaScript?](#what-is-the-difference-between-pass-by-value-and-pass-by-reference-in-javascript)


# Theory
|Type|	typeof return value|	Object wrapper|
|---|---|---|
|Null	|"object"	|N/A|
|Undefined	|"undefined"	|N/A|
|Boolean	|"boolean"	|Boolean|
|Number	|"number"	|Number|
|BigInt	|"bigint"	|BigInt|
|String	|"string"	|String|
|Symbol	|"symbol"	|Symbol|

# Interview Questions

## What are the primitive data types in JavaScript?
In JavaScript, a primitive (primitive value, primitive data type) is data that is not an object and has no methods or properties. There are 7 primitive data types:

|Type|	typeof return value|	Object wrapper|
|---|---|---|
|Null	|"object"	|N/A|
|Undefined	|"undefined"	|N/A|
|Boolean	|"boolean"	|Boolean|
|Number	|"number"	|Number|
|BigInt	|"bigint"	|BigInt|
|String	|"string"	|String|
|Symbol	|"symbol"	|Symbol|


## What is the difference between null and undefined in JavaScript?
In JavaScript, `null` and `undefined` are two distinct values that represent different concepts.

1. **`null`**: The value `null` is a primitive value that represents the intentional absence of any object value. It is typically used to indicate that a variable or object property has no assigned value or that it has been intentionally set to null.

Example usage of `null`:

```
let value = null;
console.log(value); // Output: null
```

1. **`undefined`**: The value `undefined` represents a variable or object property that has been declared but has not been assigned a value. It is the default value of uninitialized variables and function parameters. It indicates that a variable or property exists but currently holds no value.

Example usage of `undefined`:

```
let value;
console.log(value); // Output: undefined

```

In this example, the variable `value` is declared but not assigned a value. It will have the default value of `undefined`.

Key characteristics of `undefined`:

- It is a predefined value in JavaScript.
- It represents the absence of a value due to non-assignment or lack of initialization.
- It is used as the default value for uninitialized variables, function parameters without arguments, and missing object properties.

Distinguishing characteristics:

- `null` is typically assigned explicitly to indicate the intentional absence of a value, while `undefined` usually arises when a variable or property is declared but not explicitly assigned a value.
- `null` is a value that can be assigned to a variable, while `undefined` is a default state of a variable when it has no assigned value.

In summary, `null` is used to represent the intentional absence of an object value, while `undefined` indicates the absence of an assigned value or the default state of a variable or property.

**Tricky things**

undefined == null  —————> true

undefined === null —————> false (undefined===object)

## What is NaN in JavaScript? How is it different from undefined?
In JavaScript, **`NaN`** stands for "Not a Number" and is a special value that represents the result of an invalid or undefined mathematical operation. It is a property of the global object (**`NaN`**) and is of the data type "number".

Key differences between **`NaN`** and **`undefined`**:

- **`NaN`** is a special value representing the result of an invalid or undefined mathematical operation, while **`undefined`** indicates the absence of a value or an uninitialized variable.
- **`NaN`** is of the data type "number", while **`undefined`** is its own distinct data type.
- **`NaN`** is the result of operations involving non-numeric values, while **`undefined`** typically arises when a variable or property is declared but has not been assigned a value.

**Tricky things**

NaN Comparison:
```
console.log(NaN === NaN); // Output: false
console.log(NaN !== NaN); // Output: true
console.log(NaN == NaN); // Output: false


console.log(Object.is(NaN, NaN)); // Output: true
```
```
console.log(typeof NaN); // Output: 'number'

console.log(NaN.toString()); // Output: "NaN"
```

You can use the isNaN() function or the Number.isNaN() method to determine if a value is NaN. However, note that the behavior of these approaches is slightly different.
```
console.log(isNaN(NaN)); // Output: true
console.log(Number.isNaN(NaN)); // Output: true
```


## What is the difference between == and === in JavaScript?
In JavaScript, the `==` (loose equality) and `===` (strict equality) operators are used for comparison, but they differ in how they handle data types and perform the comparison.

1. **Loose Equality (`==`)**:
The `==` operator performs a loose or abstract equality comparison. It compares two values after performing type coercion, which means it attempts to convert the operands to a common type before comparison.

Example of loose equality:
```javascript
console.log(5 == "5"); // Output: true
```

In this example, the `==` operator converts the string `"5"` to a number and performs a numerical comparison, resulting in `true`.

1. **Strict Equality (`===`)**:
The `===` operator performs a strict or identity equality comparison. It compares the values without performing type coercion and checks for both value equality and data type equality.

Example of strict equality:
```javascript
console.log(5 === "5"); // Output: false
```

In this example, the `===` operator does not perform type coercion and directly compares the values, resulting in `false` because the types are different.

It is recommended to use the `===` (strict equality) operator in JavaScript because it provides a more accurate comparison and avoids potential issues caused by type coercion. . The `==` (loose equality) operator should be used with caution and only when type coercion is intentionally desired or necessary.


**Tricky Things**
```
console.log("" == false); // Output: true
console.log("" === false); // Output: false

console.log(null == undefined); // Output: true
console.log(null === undefined); // Output: false

console.log(NaN == NaN); // Output: false
console.log(NaN === NaN); // Output: false

```

## What is type coercion in JavaScript?

Type coercion in JavaScript is the implicit conversion of values from one data type to another, typically performed by JavaScript's runtime environment. It occurs when an operator or function is applied to operands of different types, and JavaScript automatically converts one or both of the operands to a common type.

Example of type coercion in JavaScript:

```javascript
const number = 5;
const string = "10";

const result = number + string;
console.log(result); // Output: "510"


const number = 5;
const string = "10";

const result = number - string;
console.log(result); // Output: "-5"
```

In this example, the `+` operator is used to concatenate the `number` variable and the `string` variable. However, JavaScript performs type coercion and converts the `number` to a string before concatenating them. The result is the concatenation of the string representations of both values.

**Tricky questions related to type coercion:**

1. **Question**: What is the result of `true + true`?
   **Answer**: The result is `2`. JavaScript converts `true` to the number `1` during addition.

2. **Question**: What is the result of `"5" - 3`?
   **Answer**: The result is `2`. JavaScript converts the string `"5"` to the number `5` before subtraction.

3. **Question**: What is the result of `null + 5`?
   **Answer**: The result is `5`. JavaScript converts `null` to the number `0` during addition.

4. **Question**: What is the result of `"" == 0`?
   **Answer**: The result is `true`. JavaScript converts the empty string `""` to the number `0` during loose equality comparison.

5. **Question**: What is the result of `[] == false`?
   **Answer**: The result is `true`. JavaScript converts an empty array `[]` to an empty string `""`, which is then converted to the number `0` during loose equality comparison with `false`.

6. **Question**: What is the result of `null == undefined`?
   **Answer**: The result is `true`. JavaScript considers `null` and `undefined` loosely equal.

7. **Question**: What is the result of `"true" == true`?
   **Answer**: The result is `false`. JavaScript does not perform type coercion between strings and booleans during loose equality comparison.

8. **Question**: What is the result of `"10" * 2`?
   **Answer**: The result is `20`. JavaScript converts the string `"10"` to the number `10` before multiplication.

9. **Question**: What is the result of `false + true`?
   **Answer**: The result is `1`. JavaScript converts `false` to the number `0` and `true` to the number `1` during addition.

10. **Question**: What is the result of `undefined + undefined`?
    **Answer**: The result is `NaN`. JavaScript converts `undefined` to `NaN` during addition.


## How do you create a new object in JavaScript?

In JavaScript, there are multiple ways to create a new object. Here are some common approaches:

1. **Object Literal**:
   You can create a new object using object literal notation by enclosing key-value pairs within curly braces `{}`. This is the simplest way to create an object.

   ```javascript
   const person = {
     name: "John",
     age: 30,
     profession: "Developer"
   };
   ```

2. **Constructor Function**:
   You can define a constructor function and use the `new` keyword to create instances of an object. Inside the constructor function, you can define properties and methods for the object.

   ```javascript
   function Person(name, age) {
     this.name = name;
     this.age = age;
   }

   const person = new Person("John", 30);
   ```

3. **Class** (ES6+):
   With the introduction of ES6 (ECMAScript 2015), JavaScript supports the class syntax for creating objects. Classes provide a more structured and convenient way to define objects.

   ```javascript
   class Person {
     constructor(name, age) {
       this.name = name;
       this.age = age;
     }
   }

   const person = new Person("John", 30);
   ```

4. **Object.create()**:
   The `Object.create()` method allows you to create a new object with a specified prototype object.

   ```javascript
   const personPrototype = {
     greet: function() {
       console.log("Hello!");
     }
   };

   const person = Object.create(personPrototype);
   person.name = "John";
   person.age = 30;
   ```

**Tricky Questions**


1. **Question**: What is the difference between using object literal notation and a constructor function to create an object?

**Answer**: Object literal notation allows you to create a single object directly, while a constructor function can be used to create multiple instances of an object with shared properties and methods.

2. **Question**: Can you add new properties or methods to an object created using object literal notation or a constructor function?

**Answer**: Yes, you can add new properties or methods to an object even after it has been created.

3. **Question**: Is it possible to create an object without any properties or methods?

**Answer**: Yes, you can create an object without any initial properties or methods, and then add them later as needed.

4. **Question**: How can you create an object with a specific prototype in JavaScript?

**Answer**: You can use the `Object.create()` method to create a new object with a specified prototype.

5. **Question**: What happens if you forget to use the `new` keyword when creating an object with a constructor function?

**Answer**: Without the `new` keyword, the `this` keyword inside the constructor function will refer to the global object (`window` in a browser environment), leading to unintended consequences or errors.

1. **Question**: How can you create a new object that inherits from an existing object?

**Answer**: You can use techniques like `Object.create()`, constructor functions with prototypal inheritance, or the class syntax to create a new object that inherits from an existing object or prototype.

8. **Question**: Can you create an object without a prototype in JavaScript?

**Answer**: Every object in JavaScript has a prototype, which may be either the default `Object.prototype` or a specific object set as its prototype using techniques like `Object.create()`.

9. **Question**: What is the purpose of a constructor function or class in creating objects?

**Answer**: Constructor functions and classes provide a blueprint or template for creating objects. They allow you to define properties, initialize values, and encapsulate related functionality.


## What is the difference between truthy and falsy values in JavaScript?

In JavaScript, values are evaluated as either truthy or falsy in boolean contexts. The distinction between truthy and falsy values determines their behavior in conditional statements and logical operations. Here are the key differences:

1. **Truthy Values**:
   - Truthy values are those that evaluate to `true` in a boolean context.
   - Examples of truthy values include non-empty strings, non-zero numbers, objects, arrays, functions, and any other value that is not explicitly falsy.
   - When used in an `if` statement or other boolean expressions, truthy values execute the corresponding block of code.

2. **Falsy Values**:
   - Falsy values are those that evaluate to `false` in a boolean context.
   - Examples of falsy values include `false`, `0`, an empty string `""`, `null`, `undefined`, and `NaN`.
   - When used in an `if` statement or other boolean expressions, falsy values skip the corresponding block of code and move to the next execution branch.

Examples of truthy and falsy values in JavaScript:

```javascript
if ("Hello") {
  console.log("This is truthy."); // Output: This is truthy.
}

if (0) {
  console.log("This is falsy."); // Not executed
}

console.log(Boolean("Hello")); // Output: true
console.log(Boolean(0)); // Output: false
```

##  What is the difference between pass-by-value and pass-by-reference in JavaScript?
In JavaScript, primitive values (numbers, booleans, strings) are passed by value, meaning a copy of the value is passed. Objects and arrays are passed by reference, meaning a reference to the original object or array is passed.


