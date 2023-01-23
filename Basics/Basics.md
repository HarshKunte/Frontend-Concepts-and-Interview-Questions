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


## What is the difference between == and === operators?
JavaScript provides both strict(===, !==) and type-converting(==, !=) equality comparison. The strict operators take type of variable in consideration, while non-strict operators make type correction/conversion based upon values of variables

## What is the purpose of the array slice method?
The slice() method returns the selected elements in an array as a new array object. It selects the elements starting at the given start argument, and ends at the given optional end argument without including the last element. If you omit the second argument then it selects till the end.
Note: Slice method won't mutate the original array but it returns the subset as a new array.

## What is the purpose of the array splice method?
The splice() method is used either adds or removes items from an array, and then returns the removed item. 
The first argument specifies the array position for insertion or deletion whereas the optional second argument indicates the number of elements to be deleted. Each additional argument is added to the array.
Note: Splice method modifies the original array and returns the deleted array.



## List some features of JavaScript.

Who developed JavaScript, and what was the first name of JavaScript?

JavaScript was developed by Brendan Eich, who was a Netscape programmer. Brendan Eich developed this new scripting language in just ten days in the year September 1995. At the time of its launch, JavaScript was initially called Mocha. After that, it was called Live Script and later known as JavaScript.

## List some of the advantages of JavaScript.

Some of the advantages of JavaScript are:

    Server interaction is less
    Feedback to the visitors is immediate
    Interactivity is high
    Interfaces are richer


## List some of the disadvantages of JavaScript.
Some of the disadvantages of JavaScript are:

    No support for multithreading
    No support for multiprocessing
    Reading and writing of files is not allowed
    No support for networking applications.


## What is ECMAScript ?
ECMAScript is the scripting language that forms the basis of JavaScript. ECMAScript standardized by the ECMA International standards organization in the ECMA-262 and ECMA-402 specifications. The first edition of ECMAScript was released in 1997. 



## Type coercion in JS
  Type coercion means when operands to the left and right of the operator have different type , one of them will be converted into an equivalent value by the Javascript engine.

  For example
  1 == '1'

  In this JS will convert '1' to 1.
  1==1 //true

  But when we use === in JS, it means that dont use type coercion and compare the values explicitly

  Object.is() is also used to compare. But it is used to check some weird cases as well

  For example

  -0 === +0 //true
  Object.is(-0, +0) //false

  NaN === NaN  //false
  Object.is(NaN, NaN)  //true



## What are PWAs ?
Progressive web applications (PWAs) are a type of mobile app delivered through the web, built using common web technologies including HTML, CSS and JavaScript. These PWAs are deployed to servers, accessible through URLs, and indexed by search engines.

## What is V8 JavaScript engine ?
V8 is an open source high-performance JavaScript engine used by the Google Chrome browser, written in C++. It is also being used in the node.js project. It implements ECMAScript and WebAssembly, and runs on Windows 7 or later, macOS 10.12+, and Linux systems that use x64, IA-32, ARM, or MIPS processors. Note: It can run standalone, or can be embedded into any C++ application.

## What is jQuery ?
jQuery is a popular cross-browser JavaScript library that provides Document Object Model (DOM) traversal, event handling, animations and AJAX interactions by minimizing the discrepancies across browsers. It is widely famous with its philosophy of “Write less, do more”.
