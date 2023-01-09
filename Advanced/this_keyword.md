## this keyword 

**'this' is the object that the function is property of**. Refers to the object which called the function in which this is called. If called outsied of any function refers to the window object.
**this keyword is dynamically scoped**, ie. no matter where it is defined the value of 'this' depends from where its called.

predict output
```
1.
const a = function() {
	console. log(this)
const b = function() {
console. log(this)
const c{
hi: function() {
console. log(this)
}
c.hi()
}
b()
}

a() 

Output
Window{}
Window{}
c:{hi:f}


2.
const obj = {name: 'Billy',
	sing() {
		console.log('a',this) ;
		var anotherFunc: function(){
			console.log('b',this)
		}
		anotherFunc()
	}
}
obj.sing()

Output 
'a' obj:{}
'b' Window

This happens because this keyword is dynamically scoped when function() is used to define the function

If we use an arrow function 'this' keyword is lexically scoped

const obj = {name: 'Billy',
	sing() {
		console.log('a',this) ;
		var anotherFunc: () =>{
			console.log('b',this)
		}
		anotherFunc()
	}
}
obj.sing()

Output:
'a' obj:{}
'b' obj:{}
```

So in the above example when we change the function to an arrow function, 'this' keyword is lexically bind
so it checks where it is currently when its called. hence it points to obj object.



Predict the output
```
1.
var a ={
name:'jay',
say():{console.log(this)}
},
var b ={
name:'jay',
say():{return function() {console.log(this)}}
},
var c ={
name:'jay',
say():{return () => console.log(this)}
},

a.say(); // a:{}
b.say(); // window
c.say(); // c:{}
```

