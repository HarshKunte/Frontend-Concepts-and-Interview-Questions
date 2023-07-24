# Theory


**'this' is the object that the function is property of**. Refers to the object which called the function in which this is called. If called outsied of any function refers to the window object.
**this keyword is dynamically scoped**, ie. no matter where it is defined the value of 'this' depends from where its called.

### 4 ways of binding 'this'

1. using 'new'
new keyword binds this to the object that we instantiate.

```
// new binding this
function Person(name, age) {
this.name= name;
this.age = age;
}

const personl = new Person( 'Xavier',55)
```

2. implicit binding
it is how the language is defined. It points to the object created.
It is most common way.
```
// implicit binding
const person = {
	name: 'Karen',
	age: 40,
	hi() {
	console. log( 'hi'+ this.name)
	}
}
```

3. explicit binding
when we explicitly bind a specific object to 'this'
```
const person3 = {
	name: 'Karen' ,
	age: 40,
	hi: function() {
	console. log( 'hi'+ this.setTimeout).bind(window) 
	// here we are binding this to 'window' object, originally it points to the object person 3
	}
}
```

4. arrow functions
 All the other times 'this' is dynamically i.e. whereever it gets called it decides the value
 But using arrow function we can lexically scope 'this' keyword

 ```
 // arrow function
const person4 = {
	name: 'Karen',
	age: 40,
	hi: function() {
		var inner = () =>{
			console. log( 'hi'+ this. name)
		}
	return inner()
}}
// here when we use arrow function of inner function we are lexically scoping this which points to the object
// but when we use a function keyword to define the inner function 'this' will point to 'window' object
 ```


# Predict the output 
```javascript
1.
const a = function() {
	console.log(this)
    const b = function() {
        console.log(this)
        const c = {
            hi: function() {
            console.log(this)
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
```javascript
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
