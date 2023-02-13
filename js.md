res.data 为服务器端返回的数据

for 循环 for（，，）{

                   }

do{ 
    语句
}
while(条件)

<!-- <button onclick> -->

js调试:  console.log()

提前声明变量，否则会出现undifine

=== 恒等计算符，同时检查表达式的值和类型

switch语句用恒等计算符进行比较（===）

js中所有的数据都以float 类型来存储

var 只有全局变量和局部变量  ，let只对块内部的代码生效，————{}内
{ 
    let x = 2;
}
// 这里不能使用 x 变量

var可以先使用再声明，let只能先声明再使用

const 常量不能通过再赋值修改，也不能再次声明，需要先声明再使用

json是js对象的字符串表示法

var obj = JSON.parse(text);  将字符串转换为JavaScript对象

void  计算一个表达式，但不返回任何值

async 异步回调
# arr方法
### .join()
将数组中的所有元素转为一个字符串，分隔符由括号内容决定
### .toString()
返回一个字符串，字符串内容即数组内容
### .unshift()
将一个或多个元素加到数组头部，返回长度
### .splice(start, deleteCount, item1, item2, itemN)
从索引值start的位置开始，删除count个值，并插入后面的item
### .filter()
过滤，浅拷贝
### .map()
不修改原数组的值，创建一个新数组
### .copyWithin(target, start, end)

### .reduce()
计算数组所有元素的总和

### .some()
测试数组中是不是至少有一个元素通过提供的测试函数，返回一个boolean

### .shift()
删除首个项，返回被删除的项

this.ryjglist2.push({name:listname[index],value:item})

delete 删除对象的某个属性

# 什么是重绘和回流
## 回流:
当渲染树中部分或者全部元素的尺寸、结构或者属性发生变化时，浏览器会重新渲染部分或者全部文档的过程就称为回流。
## 重绘
当页面中某些元素的样式发生变化，但是不会影响其在文档流中的位置时，浏览器就会对元素进行重新绘制，这个过程就是重绘。


注意： 当触发回流时，一定会触发重绘，但是重绘不一定会引发回流。

定时器-setTimeout

[JavaScript节流与防抖](https://www.cnblogs.com/yanggeng/p/10753837.html)

https://www.cnblogs.com/momo798/p/9177767.html

时间戳-记录当前时间和上次发生的时间计算时间差，在固定时间差，进行某些行为

- 防抖：（在执行完后，计时一段时间再执行）

```js
/*
* fn [function] 需要防抖的函数
* delay [number] 毫秒，防抖期限值
*/
function debounce(fn,delay){
    let timer = null //借助闭包
    return function() {
        if(timer){
            clearTimeout(timer) //进入该分支语句，说明当前正在一个计时过程中，并且又触发了相同事件。所以要取消当前的计时，重新开始计时
            timer = setTimeout(fn,delay) 
        }else{
            timer = setTimeout(fn,delay) // 进入该分支说明当前并没有在计时，那么就开始一个计时
        }
    }
}
```

- 节流（**让函数执行一次后，在某个时间段内暂时失效，过了这段时间后再重新激活**（类似于技能冷却时间）。）

```js
function shijianchuo(fn, wait){
    var pre = new Date();
    return function(){
        var that = this;//由于匿名函数，this指向window
        var args = arguments;//回调函数的fn中的参数
        var now = new Date();
        if(now - pre >= wait){
            fn.apply(that, args);
        }
    }
}
function fn(){
    console.log('时间戳')
}
window.addEventListener('scroll', shijianchuo(fn, 1000));
```


- es6扩展运算符
```js
console.log(...[1, 2, 3])
// 1 2 3
console.log(...[1, [2, 3, 4], 5])
// 1 [2, 3, 4] 5
```
