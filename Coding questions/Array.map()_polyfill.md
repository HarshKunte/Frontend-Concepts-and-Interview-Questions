# Polyfill for Array.prototype.map


### Edge Cases
- Passing the index and array to the map callback.
- Calling the map callback with the correct this if thisArg is specified.
- Sparse arrays (e.g. [1, 2, , 4]). The empty values should be ignored while traversing the array.


```
Array.prototype.myMap = function (callbackFn, thisArg) {
  const len = this.length
  const res = []

  for(let k=0;k<len;k++){
    const val = this[k]

    if(Object.hasOwn(this, k) ){
      const newVal = callbackFn.call(thisArg, val, k, this)
      res.push(newVal)
    }
    else{
      res.push(val)
    }
  }

  return res;
};
```