title: map与foreach
author: John Doe
tags:
  - VanillaJs
  - Map
  - Foreach
categories:
  - Javascript
date: 2021-11-11 09:37:00
---
## 区别？

Array.forEach()改变原数组，Array.map()则不改变原数组，返回新对象，但在实践中，发现只有基础数据类型不会被改变，
引用数据类型则还是会被改变。

例:

```
let a = [1,2,3,4,5]
a.map(n => {
  n = n * 2
})
console.log(a) // [1, 2, 3, 4, 5]

let b = [{ a: 1 }, { a: 2 }, { a: 3 }, { a: 4 }, { a: 5 }]
b.map((v) => {
  v.a = v.a * 2
})
console.log(JSON.stringify(b)) // [{"a":2},{"a":4},{"a":6},{"a":8},{"a":10}]
```

### 以下内容摘取CSDN

map():
map方法返回一个新的数组，数组中的元素为原始数组调用函数处理后的值

也就是map()进行处理之后返回一个新的数组

⚠️注意：map()方法不会对空数组进行检测

map方法不会改变原始数组

forEach()

forEach方法用于调用数组的每个元素，将元素传给回调函数

⚠️注意： forEach对于空数组是不会调用回调函数的 ，

没有返回一个新数组&没有返回值

应用场景：为一些相同的元素，绑定事件处理器！

不可链式调用

## 执行速度

### 摘自CSDN

jsPref是一个非常好的网站用来比较不同的JavaScript函数的执行速度。

这里是forEach()和map()的测试结果：

可以看到，在我到电脑上forEach()的执行速度比map()慢了70%。每个人的浏览器的执行结果会不一样。你可以使用下面的链接来测试一下: Map vs. forEach - jsPref。

JavaScript太灵活了，出了BUG你也不知道，不妨接入Fundebug线上实时监控。

函数式角度的理解

如果你习惯使用函数是编程，那么肯定喜欢使用map()。因为forEach()会改变原始的数组的值，而map()会返回一个全新的数组，原本的数组不受到影响。

哪个更好呢？

取决于你想要做什么。

forEach适合于你并不打算改变数据的时候，而只是想用数据做一些事情 – 比如存入数据库或则打印出来。

## 理解

map性能强于forEach，且能链式操作，forEach适合不改变数据，只想拿数据做一些判断时
对数据做操作优先用map