# Event loop in JS

The event loop is a key part of the JavaScript runtime environment. It's responsible for handling asynchronous operations, such as callbacks, promises, and async/await.

Here's a basic diagram of the event loop:

1. Stack - where the JavaScript engine keeps track of what function is currently running and its internal calls.
2. Web APIs - where asynchronous callbacks are placed after being called and waiting for their condition to be met.
3. Callback Queue (Task Queue) - where callbacks are placed after their conditions are met in the Web APIs.
4. Event Loop - checks if the stack is empty. If it is, it pushes the first function in the callback queue to the stack.