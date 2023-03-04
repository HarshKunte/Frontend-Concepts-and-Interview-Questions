### 1. Convert callback function to promise
```
const asyncFunc = (callback) =>{
  setTimeout(()=>{
    callback(1)
  },3000)
}

const promiseFunc = () =>{
  
  return new Promise((resolve)=>{
    asyncFunc((data) =>{
      resolve(data)
    })
  })
} 

promiseFunc().then(res => console.log(res))
```