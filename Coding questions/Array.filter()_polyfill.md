# Polufill for Array.prototype.filter

```
Array.prototype.myFilter = function (callbackFn, thisArg) {
  const results = []
  const len = this.length
  for(let k = 0;k<len;k++){
    const val = this[k];

    if(Object.hasOwn(this, k) && callbackFn.call(thisArg, val, k, this)){
      results.push(val)
    }
  }

  return results;
};
```