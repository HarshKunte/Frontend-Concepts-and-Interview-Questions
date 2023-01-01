### 1. **What is the purpose of the array splice method?**
The splice() method is used either adds or removes items from an array, and then returns the removed item. 
The first argument specifies the array position for insertion or deletion whereas the optional second argument indicates the number of elements to be deleted. Each additional argument is added to the array.
Note: Splice method modifies the original array and returns the deleted array.

## 2. **What is the purpose of the array slice method?**
The slice() method returns the selected elements in an array as a new array object. It selects the elements starting at the given start argument, and ends at the given optional end argument without including the last element. If you omit the second argument then it selects till the end.
Note: Slice method won't mutate the original array but it returns the subset as a new array.

## 3. **What is the difference between == and === operators?**
JavaScript provides both strict(===, !==) and type-converting(==, !=) equality comparison. The strict operators take type of variable in consideration, while non-strict operators make type correction/conversion based upon values of variables

## 4. **What is a Cookie?**
A cookie is a piece of data that is stored on your computer to be accessed by your browser. Cookies are saved as key/value pairs.

## 5. **Why do you need a Cookie?**
Cookies are used to remember information such as the user profile(such as username).

## 6. **What is the main difference between localStorage and sessionStorage?**
LocalStorage is the same as SessionStorage but it persists the data even when the browser is closed and reopened(i.e it has no expiration time) whereas in sessionStorage data gets cleared when the page session ends.

## 7. **What is IIFE(Immediately Invoked Function Expression)?**
IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined.
Example:
(function () {
  // logic here
})();

## 8. **What is a promise?**
A promise is an object that may produce a single value some time in the future with either a resolved value or a reason that it’s not resolved(for example, network error). It will be in one of the 3 possible states: fulfilled, rejected, or pending.
