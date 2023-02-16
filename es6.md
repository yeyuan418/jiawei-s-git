## 箭头函数：
适合与this无关的回调
var f = v => v;  等价于  var f = function(a){ return a; }
  
map 对象保存键值对，


new set(arr)  可以去除数组中的重复值，两个数组的交集，并集，差集

let 只在块级作用域中有用，不存在变量提升

## const 声明常量
对数组和对象的元素修改，不算做对常量的修改，不会报错

## rest 代替arguments 来获取实参

# symbol 创建
不能与其他数据进行运算

# [... new Set(array)]
去除数组重复成员
=> 

# [... new Set('ababbc')].join('')
去除字符串重复字符  .join(),将数组内的元素转化为字符串，默认以，隔开
=> "abc"

# set类似于数组
    Set.prototype.keys()：返回键名的遍历器
    Set.prototype.values()：返回键值的遍历器
    Set.prototype.entries()：返回键值对的遍历器
    Set.prototype.forEach()：使用回调函数遍历每个成员

Array.from 可以将Set结构转为数组

# WeakSet
  成员只能是对象
  

# Map()
可以将对象作为键，不局限与对象结构的字符串-字符串形式。


# class
构造函数，可以让类中有对象上的方法和数据，实际上就是定义一个对象模板，上面有数据和方法，方法在对象的原型上 
