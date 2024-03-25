unshift() 方法将指定元素添加到数组的开头，并返回数组的新长度。

```js
const array1 = [1, 2, 3];

console.log(array1.unshift(4, 5));
// Expected output: 5

console.log(array1);
// Expected output: Array [4, 5, 1, 2, 3]

```

#### 自定义实现

```js
Array.prototype.myUnshift = function () {
  const len = arguments.length;
  for (let i = len -1; i >= 0; i--) {
    const element = arguments[i];
    this.splice(0,0,element);
  }
  return this.length;
}

let arr = [1,2,3];
console.log(arr.myUnshift(4,5),arr);
// 5 [4, 5, 1, 2, 3]
```