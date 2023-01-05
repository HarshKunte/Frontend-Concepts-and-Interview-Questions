## **Lexical scope and scope chaining -**

Lexical scope is the data or variables available where the function was defined.
Lexcial scope is ability of child function able to access the scope of parent function.
An items lexical scope is the area where it got defined(static scope) and not where its getting called(dynamic scope).

```
var x = 1;

function a(){
	var x = 2;
	function b(){
		console.log(x);
	}
}
a();
// output => 2
```

Scope chain means child function has access to all the variables available in scope parent variable and hence in similar the scope of parent gets chained with its own parent and so child also has access to grand parents scope.
So if the child cannot  find a variable in parents scope it will look into grand parents scope....this can go digging till it reaches the Global scope.

### **Function scope and Block scope**
function scope-
By default JS is function scoped. Function scope the variable declared inside function cannot be accessed outside function.

block scope -
Block means '{}'. variables decalred inside this block cannot be accessed outside block. 
Let and const variables are block scoped.
For example if a let variable is defined inside if block or for loop it will be only accessible inside those blocks.
But variables decalred using 'var' can be outside of the block too as they are function scoped.