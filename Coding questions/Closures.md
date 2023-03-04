## Implement a debounce function

```
const debounce = (func, timeout) =>{
    let timer;
    return ( ...args) => {
        console.log("inner fn", args);
        clearTimeout(timer);
        timer = setTimeout(()=> {
        func.apply(this, args);
        } , timeout);
    }
}
```


## Implement throttle function

```
const throttle = (func, timeout) =>{
    let isWaiting = false;
    return (...args) => {
        if (!isWaiting) {
        func.apply(this, args);
        isWaiting = true;
        setTimeout(() => {
        isWaiting = false
        } , timeout);
    }
}
```

## Implement memoized (caching) function

// Design a memoization function which adds 10 to provided value and take it from cache if it was already calculated.
```
const memoizeAdd = () =>{
    let cache =
    return (value) {
        if (value in cache) {
        console.log("fetching from cache");
        return cache [value] ;
        }
        else {
        console.log("calculating results");
        const result = value + 10;
        cache[value] = result;
        return result;
        }
    }
}
const newAdd = memoizeAdd();

console.log(newAdd(9)) // output:19 calculated
console.log(newAdd(9)) // output:19 cache

```