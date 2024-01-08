## **Execution context -**

When JS sees a function it creates an execution context for it. Each time a new function is called a new execution context is pushed into the stack and when the execution is completed that context is popped off from stack.

Global execution context is always present. Anything executing in JS outside of a function is executed in Global execution context.
Javascript engine creates Global execution context at start and it gives us Global Object and "this" keyword.

In browser "window"(Global object) and "this" can be accessed even with empty JS file.

Note - this === window is true