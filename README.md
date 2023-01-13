### What is the difference between == and === operators?
JavaScript provides both strict(===, !==) and type-converting(==, !=) equality comparison. The strict operators take type of variable in consideration, while non-strict operators make type correction/conversion based upon values of variables

### What is the purpose of the array slice method?
The slice() method returns the selected elements in an array as a new array object. It selects the elements starting at the given start argument, and ends at the given optional end argument without including the last element. If you omit the second argument then it selects till the end.
Note: Slice method won't mutate the original array but it returns the subset as a new array.

### What is the purpose of the array splice method?
The splice() method is used either adds or removes items from an array, and then returns the removed item. 
The first argument specifies the array position for insertion or deletion whereas the optional second argument indicates the number of elements to be deleted. Each additional argument is added to the array.
Note: Splice method modifies the original array and returns the deleted array.
