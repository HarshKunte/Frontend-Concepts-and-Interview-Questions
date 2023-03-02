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