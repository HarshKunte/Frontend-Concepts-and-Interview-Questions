# Polyfill for bind() method using call()

```
Function.prototype.myBind = function (thisArg, ...argArray) {
  const thisVar = this
   return function(...args){
      return thisVar.call(thisArg, ...argArray, ...args)
   }
};
```