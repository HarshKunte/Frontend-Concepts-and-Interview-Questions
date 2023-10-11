### Polyfill for map and reduce methods of Array

```javascript
Array.prototype.myMap = function(callback){
  let res = []
  for(let i=0;i<this.length;i++){
    res.push(callback(this[i]));
  }
  
  return res;
}

Array.prototype.myReduce = function(callback, initialVal){
  let res = initialVal!=undefined? initialVal : undefined;
  for(let i=0;i<this.length;i++){
   if(res!=undefined)
   res = callback(res, this[i], i, this);
   else
   res = this[i];
   
  }
  
  return res;
}



let arr = [1,2,3,4,5];

console.log(arr.myMap((elem)=> elem*2));
console.log(arr.myReduce((acc, curr, index)=> acc + curr+index, 0));
```