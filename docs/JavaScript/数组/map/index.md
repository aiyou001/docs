map()经常用来遍历数据。

map()的作用就是“映射”，也就是原数组被“映射”成对应新数组。

### 方法概述
- map() 方法返回一个新数组，这个新数组：由原数组中的每个元素调用一个指定方法后的返回值组成的新数组。
- map() 不会对空数组进行检测。
- map() 不会改变原始数组。
```js
 var arr = ["a","b","c","d","e"];
        arr.map(function(currentValue,index,arr){
            console.log("当前元素"+currentValue)
　　　　　　 console.log("当前索引"+index)
            console.log("数组对象"+arr)
        })
```

### 数据项求平方
```js
// 例子数值项求平方
let data = [1,2,3,4,5];
let newData = data.map(function (item){
    return item * item;

});
console.log(newData);
//箭头函数的写法
let newData2 = data.map(item => item *item);
console.log(newData2);
```

### 获得数组对象中的特定属性值
```js
// 在实际中，我们可以利用map方法方便获得数组对象中的特定属性值
let users = [
    {"name": "张小花", "email": "zhang@qq.com"},
    {"name": "body", "email": "body@qq.com"},
    {"name": "李小璐", "email": "li@qq.com"}
];
let newEmail = users.map(function (item) {
    return item.name;
});
console.log(newEmail.join(','));
//第2种获取数组对象中的值
let emails = [];
users.map(function (item){
    emails.push(item.email);
});
console.log(emails);
// ["zhang@qq.com", "body@qq.com", "li@qq.com"]
```

### map()方法用箭头函数容易出现的错误
```js
var array1 = [1, 4, 9, 16];
 
const map1 = array1.map(x => {
    if (x == 4) {
        return x * 2;
    }
});
 
console.log(map1);
// 打印结果为 [undefined, 8, undefined, undefined]
```
为什么会出现三个undefined呢？而不是我预期的[1,8,9,16]。

这样写只是增加了一个条件，即x的值为4时才乘以2，之所以会出现undefined，是因为map()方法创建了一个新数组，但新数组并不是在遍历完array1后才被赋值的，而是每遍历一次就得到一个值。所以，下面这样修改后就正确了：
```js
var array1 = [1, 4, 9, 16];
 
const map1 = array1.map(x => {
    if (x == 4) {
        return x * 2;
    }
    return x;
});
```