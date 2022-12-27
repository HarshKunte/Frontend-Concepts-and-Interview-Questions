### 1. **What is JIT?**

JIT stands for Just In Time, meaning, unlike with a compiled language, such as C, where the compilation is done ahead of time (in other words, before the actual execution of the code), with JavaScript, the compilation is done during execution. 

The monitor or profiler

While the code is executed by the interpreter, this component will profile it and keep track of how many times the different statements get hit. The moment that number starts growing, it’ll mark it as “warm” and if it grows enough, it’ll mark it as “hot”. In other words, it’ll detect which parts of your code are being used the most, and then it’ll send them over to be compiled and stored.

The baseline compiler

The warm sections of your code will be compiled into bytecode, which in turn, is run by an interpreter that is optimized for that type of code. This alone will make those sections run faster, and if possible, the baseline compilation will also try to optimize the code by creating “stubs” for every instruction being analyzed.

The optimizing compiler

Finally, the optimizing compiler will take charge and turn all those isolated stubs into a group, essentially stubbing the whole function if required. This allows for the type checks to happen only once, before the function call, instead of on every loop.

### 2. **Is Javascript Interpreted languauge or compiled languagage?**

Javascript is a dynamic language. It is intrepreted during runtime by the browser but it also uses compilation for optimizing the code.
V8 engine uses JIT (Just In time ) compiler.
So to understand easily, the code wont fail until the execution reaches that stage.

For eg:
```
let func = function(){
    if(1!=1){
        consolleeee.log("fail")
    }
}
func() //does not give error as the if condition never executes
```

### 3. **What is call stack and memeory heap?**

Call Stack is used to keep track of where we are currently in the code execution. Its like a stack where a new execution context is added on top of the existing one whenever a new function is invoked. When the execution of that function is completed it is popped out from the stack.

Memory Heap is used for memory allocation.

### 4. **Is Javascript single threaded or multi threaded? OR Is Javascript synchronous or asynchronous?**

Javascript is single threaded and synchronous language. It uses Call stack which makes it single threaded and synchronous. But with the help of event-loop and promises, JavaScript is used to do asynchronous programming also.