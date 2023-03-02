## Write a function to implement shuffle i.e. shuffle array elements

```
const shuffleltems = (items) {
    return items
    .map((item)=>({sort: Math. random(), value: item }))
    .sort((iteml, item2) => iteml.sort-item2.sort)
    .map((a) a.value)
    };
```

## Implement range 
### range(1,50) ----> [1,2,3.......50]

```
const range = (a, b) =>{
    return [...Array(b).keys()].map(e=>e+1) 
}
```


## Remove duplicates from array

```
1.
const uniqueArr = (arr) =>{
    return [...new Set(arr)]
}

2.
const uniqueArr = (arr) =>{
    const result = arr.forEach((item) => {
    if (!result.includes(item)) {
        result.push(item) ;
        }
    }
    return result;
}
```

## Find number of occurences of minimum element in array
```
const arr = [1,2,3]
const minValue = Math.min(...arr)
const minArr = arr.filter(el => el=== minValue)
console.log(minArr.length)
```