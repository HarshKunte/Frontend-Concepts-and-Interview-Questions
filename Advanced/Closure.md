Closure

When a function along with its lexical scope is returned it forms a closure.

When an outer function returns an inner function, the inner function has access to the variables of its outer function, which are not released from the memory even when the outer function is done executing itself.

Hence the inner function can be called anytime later and it will still have the access to outer function variables

So variables of outer function can act like a global variable (rather protected variable which cannot be accessed by other functions but still it's value won't be reset when the inner function is called another time) which persists in the memory for that inner function.


Advantages of Closures - 

1. Memory efficiency

For example this is a below function
```
const heavyFunction = (index) =>{

    const heavyTask = new Array(7000).fill('hello') // imagine this is a very heavy task

    console.log(heavyTask[index])
}

heavyFunction(1)
// heavyFunction(1) comes into call stack
// heavyTask array is created
// prints the item
// heavyFunction(1) is popped of the stack
// heavyTask is garbage collected

heavyFunction(2)
// heavyFunction(2) comes into call stack
// heavyTask array is created
// prints the item
// heavyFunction(2) is popped of the stack
// heavyTask is garbage collected
```

So this keeps happening again and again, which is not memory efficient.

Using closure it can be fixed like this

```
const heavyFunction = () =>{

    const heavyTask = new Array(7000).fill('hello') // imagine this is a common heavy task
    return function(index){
        console.log(heavyTask[index])
    }
}

const heavyTaskWithIndex = heavyFunction()
heavyTaskWithIndex(200)

heavyTaskWithIndex(400)

heavyTaskWithIndex(600)

//In this the heavyTask array will be created only once and will be referenced commonly for all calls.

```