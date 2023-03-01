#What is currying orcreate a curried function

In currying we can split the function in multiple functions based on number of arguments.

Example - 

```
//write a curried function  
// curriedSum = curry((1,2,3)=> 1+2+3)

const curry = function(fn){
  var arity = fn.length
    return function fn1(...args){
      if(args.length>=arity){
        return fn(...args)
      }
      else{
        return function fn2(...remainingArgs){
          var finArgs = args.concat(remainingArgs)
          console.log(finArgs)
          return fn1(...finArgs)
        }
      }
    }
}

const curriedSum = curry((a,b,c)=> a+b+c)
console.log(curriedSum(2)(3,4)) //6
console.log(curriedSum(1)(2)(3))) //6
console.log(curriedSum(1,2)(3)) //6

```

Real life examples of currying

```

const get = curry((property, object)=> object[property]);
//get('id',{id:1, name:'joh'}) ----> 1

const getld = get("id");
//getId({id:1, name:'john'}) ----> 1

const map = curry((fn, values) values.map(fn));
// map(getId, [{id:1}, {id:2}]) ----> [1,2]

const getIds = map(getId);
//getIds([{id:1}, {id:2}])    ------> [1,2]
```