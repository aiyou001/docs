### promise.all()

```js
Promise.all(
  selectedRows.map((item: any) =>
    ajax({}),
  ),
)
  .then((results) => {
    const datas = results.map((result) => result.data).flat(); // 如果每个data本身就是数组，使用flat合并
    console.log('【数据】', datas);
  })
  .catch((error) => {
    // 错误处理
    console.error('Error fetching labels:', error);
  });
```