- [Interview Questions](#interview-questions)
  - [How do you create an empty object in JavaScript?](#how-do-you-create-an-empty-object-in-javascript)
  - [How do you access properties of an object in JavaScript?](#how-do-you-access-properties-of-an-object-in-javascript)
  - [What is the difference between `null` and `undefined` when accessing a non-existent property of an object?](#what-is-the-difference-between-null-and-undefined-when-accessing-a-non-existent-property-of-an-object)
  - [How do you add a new property to an existing object?](#how-do-you-add-a-new-property-to-an-existing-object)
  - [How do you check if an object has a specific property?](#how-do-you-check-if-an-object-has-a-specific-property)
  - [How do you remove a property from an object?](#how-do-you-remove-a-property-from-an-object)
  - [How do you loop through the properties of an object?](#how-do-you-loop-through-the-properties-of-an-object)
  - [What is `Object.keys()` method used for?](#what-is-objectkeys-method-used-for)
  - [What does the `Object.assign()` method do?](#what-does-the-objectassign-method-do)
  - [How do you create a shallow copy of an object?](#how-do-you-create-a-shallow-copy-of-an-object)
  - [What are getter and setter methods in objects?](#what-are-getter-and-setter-methods-in-objects)
  - [What is the `hasOwnProperty()` method used for?](#what-is-the-hasownproperty-method-used-for)
  - [How do you create an object with a specified prototype?](#how-do-you-create-an-object-with-a-specified-prototype)
  - [What is the purpose of the `Object.freeze()` method?](#what-is-the-purpose-of-the-objectfreeze-method)
  - [What is the difference between `Object.seal()` and `Object.freeze()`?](#what-is-the-difference-between-objectseal-and-objectfreeze)
  - [What will be the output of the following code?](#what-will-be-the-output-of-the-following-code)
  - [How do you create private variables in JavaScript objects?](#how-do-you-create-private-variables-in-javascript-objects)
  - [How do you check if a variable is an object or an array?](#how-do-you-check-if-a-variable-is-an-object-or-an-array)
  - [What is the difference between a method and a regular function in an object?](#what-is-the-difference-between-a-method-and-a-regular-function-in-an-object)
  - [How can you prevent object properties from being enumerated using `for...in` loop?](#how-can-you-prevent-object-properties-from-being-enumerated-using-forin-loop)

## Interview Questions
###  How do you create an empty object in JavaScript?
**Answer:** You can create an empty object using object literal notation or the `Object()` constructor.
```javascript
// Using object literal notation
const obj1 = {};

// Using Object() constructor
const obj2 = new Object();
```
###  How do you access properties of an object in JavaScript?
**Answer:** You can access object properties using dot notation or square brackets notation.
```javascript
const person = {
    name: 'John',
    age: 30
};

console.log(person.name); // Output: 'John'
console.log(person['age']); // Output: 30
```
###  What is the difference between `null` and `undefined` when accessing a non-existent property of an object?
**Answer:** When accessing a non-existent property, `undefined` is returned if the property is not defined in the object. If the object itself is `null`, trying to access any property will result in a `TypeError`.
###  How do you add a new property to an existing object?
**Answer:** You can add a new property to an object by using dot notation or square brackets notation.
```javascript
const person = { name: 'John' };
person.age = 30;
person['country'] = 'USA';
```
###  How do you check if an object has a specific property?
**Answer:** You can use the `in` operator or the `hasOwnProperty()` method to check if an object has a specific property.
```javascript
const person = { name: 'John', age: 30 };
console.log('name' in person); // Output: true
console.log(person.hasOwnProperty('age')); // Output: true
```
###  How do you remove a property from an object?
**Answer:** You can use the `delete` keyword to remove a property from an object.
```javascript
const person = { name: 'John', age: 30 };
delete person.age;
```
###  How do you loop through the properties of an object?
**Answer:** You can use a `for...in` loop to iterate through the properties of an object.
```javascript
const person = { name: 'John', age: 30 };
for (const key in person) {
    console.log(key + ': ' + person[key]);
}
```
###  What is `Object.keys()` method used for?
**Answer:** The `Object.keys()` method is used to return an array of a given object's own enumerable property names.
```javascript
const person = { name: 'John', age: 30 };
const keys = Object.keys(person);
console.log(keys); // Output: ['name', 'age']
```
###  What does the `Object.assign()` method do?
**Answer:** The `Object.assign()` method is used to copy the values of all enumerable properties from one or more source objects into a target object.
```javascript
const target = {};
const source = { name: 'John', age: 30 };
Object.assign(target, source);
console.log(target); // Output: { name: 'John', age: 30 }
```

###  How do you create a shallow copy of an object?
**Answer:** You can use the `Object.assign()` method or the spread operator to create a shallow copy of an object.
```javascript
const original = { name: 'John', age: 30 };
const copy1 = Object.assign({}, original);
const copy2 = { ...original };
```

###  What are getter and setter methods in objects?
**Answer:** Getter and setter methods allow you to define custom behavior when getting and setting the values of an object's properties.
```javascript
const person = {
    _name: 'John',
    get name() {
    return this._name;
    },
    set name(newName) {
    this._name = newName;
    }
};

console.log(person.name); // Output: 'John'
person.name = 'Alice';
console.log(person.name); // Output: 'Alice'
```

###  What is the `hasOwnProperty()` method used for?
**Answer:** The `hasOwnProperty()` method is used to check if an object has a specific property. It returns `true` if the object has the property and `false` otherwise.
```javascript
const person = { name: 'John', age: 30 };
console.log(person.hasOwnProperty('name')); // Output: true
```

###  How do you create an object with a specified prototype?
**Answer:** You can

use the `Object.create()` method to create an object with a specified prototype.
```javascript
const parent = { name: 'Parent' };
const child = Object.create(parent);
console.log(child.name); // Output: 'Parent'
```

###  What is the purpose of the `Object.freeze()` method?
**Answer:** The `Object.freeze()` method is used to make an object immutable, preventing any changes to its properties or prototype.
```javascript
const person = { name: 'John' };
Object.freeze(person);
person.age = 30; // This assignment will have no effect in strict mode or throw an error in non-strict mode
```

###  What is the difference between `Object.seal()` and `Object.freeze()`?
**Answer:** `Object.seal()` allows changes to existing properties but prevents adding or removing properties, while `Object.freeze()` makes the object completely immutable.

###  What will be the output of the following code?
```javascript
const person = {
    name: 'John',
    getName: function() {
    return this.name;
    }
};

const getName = person.getName;
console.log(getName()); // What will be the output?
```
**Answer:** The output will be `undefined`. When `getName` is called directly, without the context of the `person` object, `this` will refer to the global object (or `undefined` in strict mode), and `this.name` will be `undefined`.

###  How do you create private variables in JavaScript objects?
**Answer:** In JavaScript, you can create private variables using closures and IIFE (Immediately Invoked Function Expression).
```javascript
const person = (function() {
    let name = 'John';

    return {
    getName: function() {
        return name;
    },
    setName: function(newName) {
        name = newName;
    }
    };
})();

console.log(person.name); // Output: undefined (private variable)
console.log(person.getName()); // Output: 'John'
person.setName('Alice');
console.log(person.getName()); // Output: 'Alice'
```

###  How do you check if a variable is an object or an array?
**Answer:** You can use the `typeof` operator and the `Array.isArray()` method to check if a variable is an object or an array.
```javascript
const obj = { name: 'John' };
const arr = [1, 2, 3];

console.log(typeof obj === 'object'); // Output: true
console.log(Array.isArray(arr)); // Output: true
```

###  What is the difference between a method and a regular function in an object?
    **Answer:** A method is a function that is a property of an object. It is invoked using the dot notation and has access to the object's properties using the `this` keyword.

###  How can you prevent object properties from being enumerated using `for...in` loop?
**Answer:** You can define object properties with the `enumerable` attribute set to `false`, which prevents them from being enumerated by `for...in` loop or `Object.keys()`.
```javascript
const obj = {
    name: 'John',
    age: 30
};

Object.defineProperty(obj, 'country', {
    value: 'USA',
    enumerable: false
});

for (const key in obj) {
    console.log(key); // Output: 'name', 'age' (country property is not enumerated)
}
```