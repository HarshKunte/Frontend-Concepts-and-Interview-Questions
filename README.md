### What is prototype chaining?
Prototype chaining is used to build new types of object based on existing one’s.
It is similar to inheritance in class based languages like C++ and Java.

It means that new instance of any object inherits the properties/methods of the parent object. For example if we create Dog as new object this will have the properties of Object inside its proto.

The prototype on object instance is available through Object.getPrototypeOf(object) or **proto** property whereas prototype on constructors function is available through Object.prototype.


### What is the difference between == and === operators?
JavaScript provides both strict(===, !==) and type-converting(==, !=) equality comparison. The strict operators take type of variable in consideration, while non-strict operators make type correction/conversion based upon values of variables
