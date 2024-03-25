### 数组深拷贝

```js
const newArr = testArr.slice()
console.log(testArr === newArr) // false
```

### 数组去重

```js
let arr = [1, 2, 1, 3, 2, 4, 3, 5, 4]
let newArr = [...new Set(arr)]
console.log(newArr)
```

#### 对象数组去重

##### 法1

通过数组的reduce()方法对数组的对象从左到右进行处理，定义一个空对象obj{}；

如果数组当前对象的name不在obj{}，就将当前对象的name加入到空对象，并将当前对象push到积累变量total数组里；

如果当前对象的name存在obj{}，则跳过push操作。

```js
//reduce第一个参数是遍历需要执行的函数，第二个参数是item的初始值
var arr = [
  { "id": 1, "name": "张三" },
  { "id": 2, "name": "李四" },
  { "id": 3, "name": "王五" },
  { "id": 2, "name": "张三" }
];
var obj = {};
arr = arr.reduce(function(item, next) {
  obj[next.id] ? '' : obj[next.id] = true && item.push(next);
  return item;
}, []);
console.log(arr);
```
可以判断多个属性，这里判断了两个条件，（id 和 name）



##### 法2

利用set去重

```js
var arr2 = [
  {"id":1,"name":"张三"},
  {"id":2,"name":"李四"},
  {"id":3,"name":"王五"},
  {"id":2,"name":"张三"},
  {'id':4,'name':'李四'}
];

function unique(arr){
    const res= new Map()
    return arr.filter((a)=> !res.has(a.id) && res.set(a.id,1) && !res.has(a.name) && res.set(a.name,1))
}
//输出结果：
unique(arr2)
[
    {
        "id": 1,
        "name": "张三"
    },
    {
        "id": 2,
        "name": "李四"
    },
    {
        "id": 3,
        "name": "王五"
    }
]

```
