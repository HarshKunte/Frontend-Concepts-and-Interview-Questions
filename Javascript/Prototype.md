# Theory

**Prototype:**
In JavaScript, every object has an internal property called `prototype`, which is a reference to another object. This `prototype` object acts as a blueprint for the object and defines the properties and methods that the object will inherit. When you access a property or method on an object, JavaScript first looks for that property or method in the object itself. If it doesn't find it, it checks the object's `prototype`, and if it's not found there, it continues up the prototype chain until it either finds the property or reaches the top of the chain, which is typically `Object.prototype`.

**Prototypal Inheritance:**
Prototypal inheritance is a way for objects in JavaScript to inherit properties and methods from other objects. When an object is created, it inherits the properties and methods from its prototype. If a property or method is not found in the object itself, JavaScript looks up the prototype chain to find it. This creates a hierarchical chain of objects, with each object inheriting from its prototype, and the prototype itself inheriting from its prototype, forming a chain until it reaches `Object.prototype`, which is the last object in the chain.

The concept of prototypal inheritance is often referred to as the "prototype chain." If a property or method is not found in the object, JavaScript looks up the chain until it finds it or reaches the end of the chain.

**Example:**
Let's illustrate prototypal inheritance with an example:

```jsx
// Parent object (prototype)
const personPrototype = {
  greet: function() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

// Create a new object (child) inheriting from the parent prototype
const john = Object.create(personPrototype);
john.name = 'John';
john.age = 30;

// Call the inherited method
john.greet(); // Output: "Hello, my name is John"

```

In this example, `personPrototype` is the prototype object that defines the `greet` method. We then create a new object `john` using `Object.create(personPrototype)`, which sets the `john` object's prototype to `personPrototype`. As a result, `john` inherits the `greet` method from its prototype. When we call `john.greet()`, the method is found on the prototype chain, and it logs the greeting with John's name.

# Interview Questions

1. **Question:** What is the `prototype` property in JavaScript objects?
**Answer:** The `prototype` property of an object is an internal reference to another object. It defines the blueprint from which the object inherits properties and methods.
2. **Question:** How does prototypal inheritance work in JavaScript?
**Answer:** Prototypal inheritance in JavaScript allows objects to inherit properties and methods from other objects through the prototype chain.
3. **Question:** What is the relationship between an object and its prototype in JavaScript?
**Answer:** An object's prototype serves as the blueprint for the object, defining the properties and methods it inherits. The object has access to its prototype through the `__proto__` property or the `Object.getPrototypeOf()` method.
4. **Question:** How do you create an object that inherits from another object in JavaScript?
**Answer:** You can use `Object.create()` to create a new object with a specified prototype.
5. **Question:** What is the top of the prototype chain in JavaScript?
**Answer:** The top of the prototype chain is typically `Object.prototype`, which serves as the ultimate prototype for most JavaScript objects.
6. **Question:** How can you set an object's prototype to another object?
**Answer:** You can use `Object.setPrototypeOf()` to set an object's prototype to another object.
7. **Question:** What is the `constructor` property in JavaScript objects?
**Answer:** The `constructor` property is a reference to the constructor function that created the object. It is available on the object's prototype.
8. **Question:** How do you check if an object inherits from a specific prototype?
**Answer:** You can use the `instanceof` operator or the `Object.getPrototypeOf()` method to check the object's prototype chain.
9. **Question:** How can you create private properties in JavaScript objects using prototypes?
**Answer:** Private properties in JavaScript objects can be created using closures and IIFE (Immediately Invoked Function Expression).
10. **Question:** What happens when you modify the prototype of an object after creating instances of that object?
**Answer:** Modifying the prototype of an object after creating instances will affect all existing and future instances, as they share the same prototype.
11. **Question:** How can you extend the functionality of an existing object's prototype?
**Answer:** You can add new properties and methods to an existing object's prototype to extend its functionality.
12. **Question:** What is the difference between `__proto__` and `prototype`?
**Answer:** `__proto__` is a non-standard way to access an object's prototype, while `prototype` is a property found on constructor functions that are used with the `new` keyword.
13. **Question:** How do you prevent an object's properties from being accessed through its prototype chain?
**Answer:** You can use property descriptors with the `enumerable` attribute set to `false` to prevent properties from being accessed through the prototype chain.
14. **Question:** Can you create an object without a prototype?
**Answer:** Yes, you can create an object without a prototype by using `Object.create(null)` or setting `Object.setPrototypeOf(obj, null)`.
15. **Question:** What is the purpose of the `Object.prototype` object in JavaScript?
**Answer:** The `Object.prototype` object is the top-level prototype for most JavaScript objects. It contains common methods and properties that are available to all objects through the prototype chain.