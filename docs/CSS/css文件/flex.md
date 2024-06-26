基于业务自己封装的弹性盒子 sass 文件

```scss
// 弹性布局 - 横向
.flex-row {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    -webkit-box-orient: horizontal;
    -webkit-box-direction: normal;
    -ms-flex-direction: row;
    flex-direction: row;
}

// 弹性布局 - 纵向
.flex-col {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    // -webkit-box-align: center;
    // -ms-flex-align: center;
    // align-items: center;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
}

.flex {
    -webkit-box-flex: 1;
    -ms-flex: 1;
    flex: 1;
}

.flex2 {
    -webkit-box-flex: 2;
    -ms-flex: 2;
    flex: 2;
}

.flex3 {
    -webkit-box-flex: 3;
    -ms-flex: 3;
    flex: 3;
}

.flex4 {
    -webkit-box-flex: 4;
    -ms-flex: 4;
    flex: 4;
}

// 弹性布局 - 各种对齐
.flex-top {
    -webkit-box-align: initial;
    -ms-flex-align: initial;
    align-items: initial;
}

.flex-bottom {
    -webkit-box-align: baseline;
    -ms-flex-align: baseline;
    align-items: baseline;
}

.flex-center {
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
}

.just-between {
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
}

.just-around {
    -webkit-box-pack: space-evenly;
    -ms-flex-pack: space-evenly;
    justify-content: space-evenly;
}

.just-evenly {
    -webkit-box-pack: space-evenly;
    -ms-flex-pack: space-evenly;
    justify-content: space-evenly;
}

.just-end {
    -webkit-box-pack: end;
    -ms-flex-pack: end;
    justify-content: end;
}

.flex-wrap {
    flex-wrap: wrap;
}

// 行内块级
.inline-block {
    display: inline-block;
}

// 加粗
.bold {
    font-weight: bold;
}

.non-bold {
    font-weight: normal !important;
}

// 可点击标识
.clickable {
    cursor: pointer;
    &:active {
        opacity: 0.8;
    }
}

// 超链接样式
.linkable {
    @extend .clickable;
    color: #2d8cf0;
    &:hover {
        color: #57a3f3;
    }
}

// 文本居中
.tac {
    text-align: center;
}

.tal {
    text-align: left;
}

.tar {
    text-align: right;
}

// 多行省略号
@mixin ellipsis($n) {
    height: 1.5em * $n;
    line-height: 1.5em;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: $n;
    overflow: hidden;
}

// 单行省略号
.text-ellipsis-1 {
    @include ellipsis(1);
}

// 双行省略号
.text-ellipsis-2 {
    @include ellipsis(2);
}

// 三行省略号
.text-ellipsis-3 {
    @include ellipsis(3);
}

hr {
    border: none;
    border-bottom: 1px solid #d1d1d1;
}

.required {
    &:before {
        content: "*";
        color: red;
    }
}
```
