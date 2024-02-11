# Intro

The syntax for TypeScript is very similar to JavaScript. For example, you can define a variable with a specific type like this:

```tsx
let isDone: boolean = false;

```

You can also define complex types, like arrays and objects:

```tsx
let list: number[] = [1, 2, 3];
let x: [string, number] = ['hello', 10];  // Tuple

```

Functions are also typed in TypeScript:

```tsx
function add(x: number, y: number): number {
  return x + y;
}

```

These type annotations help you prevent mistakes, like passing a string to a function that expects a number, and provide better tooling support, like autocomplete and refactoring.

# Types and Interfaces

In TypeScript, you can define custom types using the `type` keyword:

```tsx
type MyString = string;
let str: MyString = 'Hello';

```

This is useful when you want to create a type that is a subset of another type, or when you want to give a more descriptive name to an existing type.

Interfaces are a powerful way to define contracts within your code and they are primarily used to define the shape of objects. Here is an example:

```tsx
interface Person {
  firstName: string;
  lastName: string;
}

function greet(person: Person) {
  return "Hello, " + person.firstName + " " + person.lastName;
}

let user = {firstName: "John", lastName: "Doe"};

console.log(greet(user));  // Output: Hello, John Doe

```

In this example, we declared a `Person` interface with `firstName` and `lastName` properties, and then used that interface as the type of the `person` parameter in the `greet` function. This ensures that any object passed to `greet` must have a `firstName` and `lastName` property.