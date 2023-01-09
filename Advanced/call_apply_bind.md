## Call, apply, bind -

call() and apply()

call() calls method of an object, substituting another object for the current object. When we want to call a method defined in one object but for another object we pass that object inside call().
call and apply are useful when borrowing methods from an object

Example
```
const wizard :{
name: 'Merlin',
health: 50,
heal() {
return this.health=100;
}
}
const archer:{
name: 'Robin Hood',
health: 30
}
wizard.heal.call(archer) // this will **immediately** call the heal method which is method of wizard object but for the archer object.
```

call() is also used for changing what 'this' keyword can contain.
arguments for a function to be called can passed to the call(obj, arg1, arg2, ....)
In apply() method arguments are passed like apply(obj, [arg1, arg2,....]) else everything is same.

bind() -

call() or apply() immediately calls the function. bind() returns the function which can be called later. bind() is useful for calling functions later on with certain context 
In our above example

wizard.heal.bind(archer, arg1, arg2, ....) //will return a new function which will 'this' context set for archer object

const healArcher = wizard.heal.bind(archer, arg1, arg2, ....)
healArcher()

In this way it can be called later.

So in the above example (refer same example used in this first to understand the issue)

```
const obj = {name: 'Billy',
	sing() {
		console.log('a',this) ;
		var anotherFunc: function(){
			console.log('b',this)
		}
		return anotherFunc.bind(this)
	}
}
obj.sing()()

Output 
'a' obj:{}
'b' obj:{}
```

So using bind, the confusion of 'this' pointing to window is solved as we bind the anotherfunc() with 'this' ie. obj object.

Usage of bind in currying

example
```
// function currying
function multiply(a,b) {
return a*b
}
let multiplyByTwo = multiply.bind(this,2)
console. log (multiplyByTwo(4)) //8

let multiplyByTen = multiply.bind(this,10)
console.log(multiplyByTen(4)) //40

```