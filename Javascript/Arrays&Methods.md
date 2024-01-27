Arrays and its Methods

- [Theory](#theory)
- [Interview Questions](#interview-questions)
  - [Easy](#easy)
    - [What is an array in JavaScript?](#what-is-an-array-in-javascript)
    - [How do you create an array in JavaScript?](#how-do-you-create-an-array-in-javascript)
    - [How do you add elements to the end of an array?](#how-do-you-add-elements-to-the-end-of-an-array)
    - [How do you remove elements from the end of an array?](#how-do-you-remove-elements-from-the-end-of-an-array)
    - [How do you loop through an array in JavaScript?](#how-do-you-loop-through-an-array-in-javascript)
    - [How do you find the index of a specific element in an array?](#how-do-you-find-the-index-of-a-specific-element-in-an-array)
    - [How do you convert an array to a string?](#how-do-you-convert-an-array-to-a-string)
  - [Medium](#medium)
    - [How do you add elements to the beginning of an array?](#how-do-you-add-elements-to-the-beginning-of-an-array)
    - [How do you sort an array in ascending and descending order?](#how-do-you-sort-an-array-in-ascending-and-descending-order)
    - [How do you remove a specific element from an array?](#how-do-you-remove-a-specific-element-from-an-array)
    - [How do you find the maximum and minimum values in an array?](#how-do-you-find-the-maximum-and-minimum-values-in-an-array)
  - [Hard](#hard)
    - [What is the difference between .forEach(), .map(), and .filter() methods in JavaScript arrays?](#what-is-the-difference-between-foreach-map-and-filter-methods-in-javascript-arrays)
    - [How do you implement a custom .map() function using .forEach()?](#how-do-you-implement-a-custom-map-function-using-foreach)
    - [How do you implement a custom .filter() function using .forEach()?](#how-do-you-implement-a-custom-filter-function-using-foreach)
    - [How do you remove duplicate elements from an array without using Set?](#how-do-you-remove-duplicate-elements-from-an-array-without-using-set)
  - [Tricky Questions](#tricky-questions)


# Theory

**Arrays in JavaScript**:
- An array is a data structure used to store multiple values in a single variable. It is a collection of elements, where each element can be of any data type (e.g., numbers, strings, objects, etc.).
- Arrays are created using square brackets `[]`. Elements are separated by commas.
- Arrays are zero-indexed, meaning the first element is accessed using index `0`, the second with index `1`, and so on.

## Ways to create Arrays -

- using `[]`
- using `new Array(<number of elements>)`
- using `Array.of( <elements>) -------> ex. Array.of( 1,2,3 ) ---> [1,2,3]`
- using `Array.from()` . useful to create array from something else

**Common Array Methods**:
1. `.push()`:
   - Adds one or more elements to the end of an array.
   - Modifies the original array and returns the new length.

2. `.pop()`:
   - Removes the last element from an array.
   - Modifies the original array and returns the removed element.

3. `.unshift()`:
   - Adds one or more elements to the beginning of an array.
   - Modifies the original array and returns the new length.

4. `.shift()`:
   - Removes the first element from an array.
   - Modifies the original array and returns the removed element.

5. `.concat()`:
   - Concatenates two or more arrays to create a new array.
   - Does not modify the original arrays.

6. `.slice()`:
   - Extracts a portion of an array into a new array.
   - Does not modify the original array.

7. `.splice()`:
   - Adds or removes elements from an array at a specified index.
   - Modifies the original array and returns the removed elements.

8. `.indexOf()` and `.lastIndexOf()`:
   - Search for an element and return its index in the array.
   - `.indexOf()` searches from the beginning, and `.lastIndexOf()` searches from the end.

9. `.forEach()`:
   - Executes a provided function once for each element in the array.
   - Does not create a new array.

10. `.map()`:
    - Creates a new array with the results of calling a provided function on every element in the array.

11. `.filter()`:
    - Creates a new array with elements that pass a test specified by a provided function.

12. `.reduce()`:
    - Executes a provided function to reduce the array to a single value.

**Array Length**:
- The `.length` property of an array returns the number of elements in the array.
- Setting `.length` to a new value can add or remove elements from the array.

**Tricky Behavior**:
- Arrays are compared by reference, not by their content. So, two separate arrays with the same elements will not be considered equal.
- Arrays can be converted to strings using `.toString()` or `.join()`, which returns a comma-separated string of array elements.


# Interview Questions

## Easy
### What is an array in JavaScript?
    
An array is a data structure used to store multiple values in a single variable. It is a collection of elements, where each element can be of any data type, such as numbers, strings, objects, or even other arrays. Arrays in JavaScript are dynamic, meaning they can grow or shrink in size as needed, and they are zero-indexed
    
### How do you create an array in JavaScript?
    
In JavaScript, there are multiple ways to create an array. Here are some common approaches:

1. **Array Literal**:
The simplest and most common way to create an array is by using an array literal, which is a list of elements enclosed in square brackets `[]`, separated by commas.
    
    ```
    const numbers = [1, 2, 3, 4, 5];
    const fruits = ["apple", "banana", "orange"];
    const mixedArray = [10, "hello", true, { name: "John" }];
    
    ```
    
2. **Array Constructor**:
You can also create an array using the `Array` constructor, which can be called with or without the `new` keyword.
    
    ```
    const numbers = new Array(1, 2, 3, 4, 5);
    const emptyArray = new Array(); // Creates an empty array
    
    ```
    
    Note: Be cautious when using the `Array` constructor without arguments, as it can lead to unexpected results.
    
3. **Array.from()** (ES6+):
The `Array.from()` method allows you to create an array from an array-like or iterable object, such as a string, Set, Map, or NodeList.
    
    ```
    const str = "hello";
    const chars = Array.from(str); // Creates an array: ["h", "e", "l", "l", "o"]
    
    ```
    
4. **Spread Operator** (ES6+):
You can use the spread operator `...` to create an array by spreading the elements of another array or iterable object.
    ```
    const arr1 = [1, 2, 3];
    const arr2 = [...arr1]; // Creates a copy of arr1: [1, 2, 3]
    ```

### How do you add elements to the end of an array?

1. **.push() method**:
   The `.push()` method appends one or more elements to the end of an array. It modifies the original array and returns the new length of the array.

   ```javascript
   const numbers = [1, 2, 3];
   numbers.push(4); // numbers is now [1, 2, 3, 4]

   // You can add multiple elements at once
   numbers.push(5, 6, 7); // numbers is now [1, 2, 3, 4, 5, 6, 7]
   ```

2. **Assignment using index**:
   You can directly assign a value to an index that is one greater than the current highest index in the array. This approach works when you want to add a single element to the end of the array.

   ```javascript
   const numbers = [1, 2, 3];
   numbers[numbers.length] = 4; // numbers is now [1, 2, 3, 4]
   ```

3. **Spread Operator and .concat() method** (ES6+):
   You can use the spread operator `...` or the `.concat()` method to create a new array that includes the existing elements along with the new elements you want to add.

   ```javascript
   const numbers = [1, 2, 3];
   const newNumbers = [...numbers, 4]; // newNumbers is [1, 2, 3, 4]

   // Using .concat() method
   const otherNumbers = numbers.concat(4); // otherNumbers is [1, 2, 3, 4]
   ```

### How do you remove elements from the end of an array?

1. **.pop() method**:
   The `.pop()` method removes the last element from the end of an array. It modifies the original array and returns the removed element.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   const removedElement = numbers.pop(); // removedElement is 5, numbers is now [1, 2, 3, 4]
   ```

2. **Using .slice() method**:
   The `.slice()` method can be used to create a new array that includes all elements of the original array except the last one.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   const newArray = numbers.slice(0, numbers.length - 1); // newArray is [1, 2, 3, 4]
   ```

3. **Assignment using index**:
   You can reassign the array by using the `.length` property to remove the last element from the array. This approach changes the length of the array, effectively removing the last element.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   numbers.length = numbers.length - 1; // numbers is now [1, 2, 3, 4]
   ```

The `.pop()` method is the most commonly used and straightforward way to remove elements from the end of an array, as it both modifies the original array and returns the removed element. If you want to keep the original array unchanged and create a new array without the last element, you can use the `.slice()` method or assign a new length to the array using the `.length` property.


### How do you loop through an array in JavaScript?

1. **for loop**:
   The traditional `for` loop is widely used for iterating through an array. You can use the loop counter variable to access each element using its index.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];

   for (let i = 0; i < numbers.length; i++) {
     console.log(numbers[i]);
   }
   ```

2. **forEach() method**:
   The `.forEach()` method is a more concise and modern way to loop through an array. It executes a provided function once for each element in the array.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];

   numbers.forEach((element) => {
     console.log(element);
   });
   ```

3. **for...of loop** (ES6+):
   The `for...of` loop provides a simpler syntax to iterate through the elements of an array. It works with any iterable, including arrays.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];

   for (const element of numbers) {
     console.log(element);
   }
   ```

4. **for...in loop** (Not recommended for arrays):
   The `for...in` loop is used to iterate over the enumerable properties of an object. Although it can be used to loop through an array, it's not recommended for arrays because it may produce unexpected results due to enumerating object properties.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];

   for (const index in numbers) {
     console.log(numbers[index]);
   }
   ```

### How do you find the index of a specific element in an array?

1. **.indexOf() method**:
   The `.indexOf()` method is used to find the index of the first occurrence of a specified element in an array. If the element is not found, it returns -1.

   ```javascript
   const numbers = [10, 20, 30, 40, 50];
   const index = numbers.indexOf(30);

   console.log(index); // Output: 2
   ```

2. **.lastIndexOf() method**:
   The `.lastIndexOf()` method is similar to `.indexOf()`, but it starts searching from the end of the array and finds the index of the last occurrence of the specified element.

   ```javascript
   const numbers = [10, 20, 30, 40, 30, 50];
   const lastIndex = numbers.lastIndexOf(30);

   console.log(lastIndex); // Output: 4
   ```

3. **.findIndex() method** (ES6+):
   The `.findIndex()` method is used to find the index of the first element that satisfies a testing function. It returns the index of the first element that returns `true` for the provided function, or -1 if no such element is found.

   ```javascript
   const numbers = [10, 20, 30, 40, 50];
   const index = numbers.findIndex((element) => element === 30);

   console.log(index); // Output: 2
   ```

4. **.indexOf() with fromIndex**:
   You can specify an optional second argument to the `.indexOf()` method to indicate the starting index from which the search should begin.

   ```javascript
   const numbers = [10, 20, 30, 40, 50];
   const index = numbers.indexOf(30, 2); // Start searching from index 2

   console.log(index); // Output: 2
   ```

### How do you convert an array to a string?

In JavaScript, you can convert an array to a string using various methods. Here are some common approaches:

1. **.toString() method**:
   The `.toString()` method is a built-in method available on arrays that converts each element of the array to a string and then joins them with commas to create a single string.

   ```javascript
   const fruits = ["apple", "banana", "orange"];
   const fruitsString = fruits.toString();

   console.log(fruitsString); // Output: "apple,banana,orange"
   ```

2. **.join() method**:
   The `.join()` method allows you to specify a separator that will be used to join the elements of the array into a string. By default, it uses a comma as the separator, but you can specify a different separator as an argument.

   ```javascript
   const fruits = ["apple", "banana", "orange"];
   const fruitsString = fruits.join(", "); // Join with a comma and space

   console.log(fruitsString); // Output: "apple, banana, orange"
   ```

3. **Using String() constructor**:
   You can use the `String()` constructor to convert an array to a string. It behaves the same way as `.toString()`.

   ```javascript
   const fruits = ["apple", "banana", "orange"];
   const fruitsString = String(fruits);

   console.log(fruitsString); // Output: "apple,banana,orange"
   ```

4. **Using .reduce() method** (Advanced):
   You can use the `.reduce()` method to concatenate the elements of the array into a string.

   ```javascript
   const fruits = ["apple", "banana", "orange"];
   const fruitsString = fruits.reduce((accumulator, current) => accumulator + ", " + current);

   console.log(fruitsString); // Output: "apple, banana, orange"
   ```

## Medium

### How do you add elements to the beginning of an array?


1. **.unshift() method**:
   The `.unshift()` method is specifically designed to add one or more elements to the beginning of an array. It modifies the original array and returns the new length of the array.

   ```javascript
   const numbers = [2, 3, 4];
   numbers.unshift(1); // numbers is now [1, 2, 3, 4]

   // You can add multiple elements at once
   numbers.unshift(-1, 0); // numbers is now [-1, 0, 1, 2, 3, 4]
   ```

2. **Assignment with spread operator** (ES6+):
   You can use the spread operator `...` to create a new array with the new elements added to the beginning, followed by the original array elements.

   ```javascript
   const numbers = [2, 3, 4];
   const newNumbers = [1, ...numbers]; // newNumbers is [1, 2, 3, 4]

   // Adding multiple elements
   const otherNumbers = [-1, 0, ...numbers]; // otherNumbers is [-1, 0, 2, 3, 4]
   ```

3. **Using .splice() method**:
   The `.splice()` method can be used to insert elements at any position in an array, including the beginning. By specifying an index of `0`, you can add elements to the beginning of the array.

   ```javascript
   const numbers = [2, 3, 4];
   numbers.splice(0, 0, 1); // numbers is now [1, 2, 3, 4]

   // Adding multiple elements
   numbers.splice(0, 0, -1, 0); // numbers is now [-1, 0, 1, 2, 3, 4]
   ```

### How do you sort an array in ascending and descending order?

In JavaScript, you can sort an array in ascending and descending order using the `.sort()` method. The `.sort()` method modifies the original array by arranging its elements in the specified order.

**Ascending Order:**

```javascript
const numbers = [5, 2, 8, 3, 1];

// Ascending order using .sort()
numbers.sort((a, b) => a - b);

console.log(numbers); // Output: [1, 2, 3, 5, 8]
```

**Descending Order:**

```javascript
const numbers = [5, 2, 8, 3, 1];

// Descending order using .sort()
numbers.sort((a, b) => b - a);

console.log(numbers); // Output: [8, 5, 3, 2, 1]
```

In both cases, we pass a comparison function to the `.sort()` method. The comparison function takes two elements, `a` and `b`, as arguments. If the return value of the comparison function is negative, `a` will come before `b` in the sorted array (for ascending order). If the return value is positive, `b` will come before `a` (for descending order). If the return value is zero, the order of the elements remains unchanged.

Remember that the `.sort()` method modifies the original array, so if you need to preserve the original array, create a copy of it before applying the `.sort()` method. You can use the spread operator or the `.slice()` method to create a copy of the array:

```javascript
const numbers = [5, 2, 8, 3, 1];

// Create a copy of the array before sorting (ascending)
const ascendingNumbers = [...numbers].sort((a, b) => a - b);

// Create a copy of the array before sorting (descending)
const descendingNumbers = numbers.slice().sort((a, b) => b - a);
```

### How do you remove a specific element from an array?

1. **.splice() method**:
   The `.splice()` method can be used to remove elements from an array by specifying the index at which the removal should start and the number of elements to be removed.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   const indexToRemove = 2; // Index of the element to remove

   numbers.splice(indexToRemove, 1); // Remove one element starting from indexToRemove

   console.log(numbers); // Output: [1, 2, 4, 5] (element "3" is removed)
   ```

2. **.filter() method**:
   The `.filter()` method creates a new array containing all elements that pass a provided test function. You can use it to create a new array without the element you want to remove.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   const elementToRemove = 3;

   const filteredNumbers = numbers.filter((element) => element !== elementToRemove);

   console.log(filteredNumbers); // Output: [1, 2, 4, 5] (element "3" is removed)
   ```

3. **Using .indexOf() and .splice()**:
   You can first find the index of the element you want to remove using the `.indexOf()` method and then use `.splice()` to remove that element.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   const elementToRemove = 3;
   const indexToRemove = numbers.indexOf(elementToRemove);

   if (indexToRemove !== -1) {
     numbers.splice(indexToRemove, 1);
   }

   console.log(numbers); // Output: [1, 2, 4, 5] (element "3" is removed)
   ```

### How do you find the maximum and minimum values in an array?

In JavaScript, you can find the maximum and minimum values in an array using the `Math.max()` and `Math.min()` functions, respectively. However, these functions work with individual numbers and not directly with arrays. To find the maximum and minimum values in an array, you can use the following methods:

**Method 1: Using Math.max() and Math.min() with the spread operator (`...`)**

```javascript
const numbers = [4, 2, 8, 3, 1];

const maxNumber = Math.max(...numbers);
const minNumber = Math.min(...numbers);

console.log(maxNumber); // Output: 8 (maximum value in the array)
console.log(minNumber); // Output: 1 (minimum value in the array)
```

**Method 2: Using .reduce() method**

```javascript
const numbers = [4, 2, 8, 3, 1];

const maxNumber = numbers.reduce((max, current) => (current > max ? current : max), numbers[0]);
const minNumber = numbers.reduce((min, current) => (current < min ? current : min), numbers[0]);

console.log(maxNumber); // Output: 8 (maximum value in the array)
console.log(minNumber); // Output: 1 (minimum value in the array)
```


## Hard

### What is the difference between .forEach(), .map(), and .filter() methods in JavaScript arrays?

1. **.forEach()**:
   - Purpose: The `.forEach()` method is used for iterating over the elements of an array and performing a specified operation (callback function) for each element.
   - Return Value: It doesn't return anything (returns `undefined`).
   - Modification of Original Array: It does not modify the original array.
   - Example:

     ```javascript
     const numbers = [1, 2, 3, 4];

     numbers.forEach((number) => {
       console.log(number * 2);
     });

     // Output:
     // 2
     // 4
     // 6
     // 8
     ```

2. **.map()**:
   - Purpose: The `.map()` method is used for creating a new array with the results of calling a provided function on every element in the original array.
   - Return Value: It returns a new array with the same length as the original array.
   - Modification of Original Array: It does not modify the original array.
   - Example:

     ```javascript
     const numbers = [1, 2, 3, 4];

     const doubledNumbers = numbers.map((number) => number * 2);
     console.log(doubledNumbers); // Output: [2, 4, 6, 8]
     ```

3. **.filter()**:
   - Purpose: The `.filter()` method is used for creating a new array with all elements that pass the test implemented by the provided function.
   - Return Value: It returns a new array containing the elements that pass the test.
   - Modification of Original Array: It does not modify the original array.
   - Example:

     ```javascript
     const numbers = [1, 2, 3, 4];

     const evenNumbers = numbers.filter((number) => number % 2 === 0);
     console.log(evenNumbers); // Output: [2, 4]
     ```

In summary, the key differences are:

- `.forEach()` is used for executing a function for each element in the array without modifying the original array.
- `.map()` is used for creating a new array based on the result of applying a function to each element of the original array.
- `.filter()` is used for creating a new array with elements that pass a specified condition defined in the provided function.


### How do you implement a custom .map() function using .forEach()?


```javascript
// Custom map function implementation
function customMap(array, callback) {
  const mappedArray = [];

  array.forEach((element) => {
    const result = callback(element);
    mappedArray.push(result);
  });

  return mappedArray;
}
```

```javascript
const numbers = [1, 2, 3, 4];

// Using customMap to double each element in the array
const doubledNumbers = customMap(numbers, (number) => number * 2);
console.log(doubledNumbers); // Output: [2, 4, 6, 8]
```


### How do you implement a custom .filter() function using .forEach()?

```javascript
// Custom filter function implementation
function customFilter(array, callback) {
  const filteredArray = [];

  array.forEach((element) => {
    if (callback(element)) {
      filteredArray.push(element);
    }
  });

  return filteredArray;
}
```

```javascript
const numbers = [1, 2, 3, 4, 5];

// Using customFilter to get even numbers from the array
const evenNumbers = customFilter(numbers, (number) => number % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```


### How do you remove duplicate elements from an array without using Set?

**Approach 1: Using .filter() and .indexOf()**

You can use the `.filter()` method in combination with the `.indexOf()` method to remove duplicates from the array. The `.indexOf()` method returns the index of the first occurrence of an element in the array. By using `.filter()` with `.indexOf()`, you can keep only the first occurrence of each element while filtering out duplicates.

```javascript
const numbers = [1, 2, 2, 3, 4, 4, 5];

const uniqueNumbers = numbers.filter((element, index, array) => array.indexOf(element) === index);

console.log(uniqueNumbers); // Output: [1, 2, 3, 4, 5]
```

**Approach 2: Using .reduce()**


```javascript
const numbers = [1, 2, 2, 3, 4, 4, 5];

const uniqueNumbers = numbers.reduce((uniqueArr, element) => {
  if (!uniqueArr.includes(element)) {
    uniqueArr.push(element);
  }
  return uniqueArr;
}, []);

console.log(uniqueNumbers); // Output: [1, 2, 3, 4, 5]
```


## Tricky Questions


1. **Question**: What is the output of **`[] + []`**?
**Answer**: The output is an empty string **`""`**. It is a result of array concatenation, where both arrays are coerced to strings and then concatenated.
1. **Question**: What is the output of **`[1, 2] + [3, 4]`**?
**Answer**: The output is **`"1,23,4"`**. Similar to the previous question, array concatenation results in string coercion and concatenation.
1. **Question**: What is the output of **`[1, 2, 3] == [1, 2, 3]`**?
**Answer**: The output is **`false`**. Arrays are compared by reference, not by their content. So, two separate arrays with the same elements will not be considered equal.
1. **Question**: What is the output of **`[1, 2, 3].length = 0`**?
**Answer**: The output is **`0`**. The **`.length`** property of an array can be used to set the new length of the array. In this case, it is set to **`0`**, effectively emptying the array.
1. **Question**: What does the expression **`[...Array(5)]`** do?
**Answer**: It creates an array with five undefined elements. The spread operator (**`...`**) is used to create a new array by spreading the elements of the newly created array of length **`5`**.

1. **Question:** What will be the output of the following code?
   ```javascript
   const arr = [1, 2, 3];
   arr[10] = 10;
   console.log(arr.length);
   ```
   **Answer:** The output will be `11`. Even though only four elements are explicitly defined in the array, when you assign a value to an index beyond the array's current length, JavaScript will automatically expand the array and update its `length` property accordingly.

2. **Question:** What is the output of the following code?
   ```javascript
   const arr = [1, 2, 3];
   arr[1] = arr[1] + arr[2];
   console.log(arr);
   ```
   **Answer:** The output will be `[1, 5, 3]`. The value at index `1` (which is `2`) is added to the value at index `2` (which is `3`) and stored back at index `1`, resulting in `[1, 5, 3]`.

3. **Question:** What will the output be when using the `.map()` method on an array with undefined elements?
   ```javascript
   const arr = [1, , 3];
   const result = arr.map(x => 2 * x);
   console.log(result);
   ```
   **Answer:** The output will be `[2, NaN, 6]`. When using `.map()`, the method applies the callback function to every element of the array, even if some elements are `undefined`. In the case of `undefined` elements, performing arithmetic operations (e.g., `2 * undefined`) results in `NaN`.

4. **Question:** What will be the output of the following code?
   ```javascript
   const arr = [1, 2, 3, 4, 5];
   arr.length = 2;
   console.log(arr);
   ```
   **Answer:** The output will be `[1, 2]`. By setting `arr.length` to `2`, you are truncating the array to have only two elements, and the elements beyond index `1` are removed.

5. **Question:** What is the result of the following code?
   ```javascript
   const arr = [10, 20, 30, 40];
   const slicedArr = arr.slice(2);
   console.log(slicedArr);
   ```
   **Answer:** The output will be `[30, 40]`. The `.slice(2)` method returns a new array containing elements from index `2` to the end of the original array, effectively removing the first two elements (`10` and `20`).

6. **Question:** What will happen when using the `.sort()` method on an array of strings with special characters?
   ```javascript
   const arr = ['apple', 'banana', 'grape', '&', '!'];
   arr.sort();
   console.log(arr);
   ```
   **Answer:** The output will be `["!", "&", "apple", "banana", "grape"]`. The `.sort()` method performs a lexicographic (alphabetical) sort by default. Special characters are sorted based on their Unicode code points, so they appear before alphanumeric characters in the sorted array.

7. **Question:** What is the output of the following code?
   ```javascript
   const arr = [1, 2, 3];
   arr.push(arr.length);
   console.log(arr);
   ```
   **Answer:** The output will be `[1, 2, 3, 3]`. The `.push()` method adds the value of `arr.length` (which is `3`) to the end of the array, resulting in `[1, 2, 3, 3]`.

8. **Question:** How can you flatten a nested array into a single array in JavaScript?
   ```javascript
   const nestedArray = [[1, 2], [3, 4], [5, 6]];
   ```
   **Answer:** One way to flatten the nested array is by using the `.flat()` method (available in modern JavaScript environments):
   ```javascript
   const flattenedArray = nestedArray.flat();
   console.log(flattenedArray); // Output: [1, 2, 3, 4, 5, 6]
   ```
   If you need to support older environments or a more manual approach, you can use `.concat(...nestedArray)` or `.reduce()` to flatten the array.

9. **Question:** What will be the output of the following code?
   ```javascript
   const arr = ['a', 'b', 'c'];
   arr[4] = 'e';
   console.log(arr);
   console.log(arr.length);
   ```
   **Answer:** The output will be `['a', 'b', 'c', undefined, 'e']` and `5`. When you assign a value to an index beyond the array's current length (index `4` in this case), JavaScript will automatically expand the array, filling the gaps with `undefined`.

10. **Question:** What happens when you call `.reverse()` on an empty array?
    ```javascript
    const arr = [];
    arr.reverse();
    console.log(arr);
    ```
    **Answer:** When you call `.reverse()` on an empty array, the array remains empty, and there are no elements to reverse. The output will be `[]`.