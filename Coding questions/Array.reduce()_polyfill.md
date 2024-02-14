# Polyfill for Array.prototype.reduce

```
Array.prototype.myReduce = function (callbackFn, initialValue) {
  const len = this.length;

  if (initialValue===undefined && len === 0) {
    throw new TypeError('Reduce of empty array with no initial value');
  }

  let acc = initialValue===undefined ? this[0] : initialValue;
  let startIndex = initialValue===undefined ? 1 : 0
  
  for(let k=startIndex;k<len;k++){
    const val = this[k]

    if(Object.hasOwn(this, k) ){
        acc = callbackFn(acc, val, k, this)
      }
      
    }
    
  return acc;
};
```