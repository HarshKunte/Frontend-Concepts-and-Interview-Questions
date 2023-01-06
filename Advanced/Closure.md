Closure

When an outer function returns an inner function, the inner function has access to the variables of its outer function, which are not released from the memory even when the outer function is done executing itself.

Hence the inner function can be called anytime later and it will still have the access to outer function variables

So variables of outer function can act like a global variable (rather protected variable which cannot be accessed by other functions but still it's value won't be reset when the inner function is called another time) which persists in the memory for that inner function.