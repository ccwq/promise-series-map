# 串行执行 function 列表 并收集结果

```javascript
const wait = timeout => {
    return new Promise(resolve => {
        setTimeout(_=>{
            console.log(timeout);
            resolve(timeout);
        }, timeout);
    })
}

Promise.$map([
    _=>wait(1000),
    _=>wait(1800),
]).then(console.log)

// 10000
// 1800
// [1000, 1800]
```