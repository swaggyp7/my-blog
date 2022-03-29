title: 箭头函数与普通函数的区别
author: YuTeng Lin
tags:
  - VanillaJs
  - ES6
categories:
  - FrontEnd
date: 2022-03-24 17:26:00
---

#### 箭头函数都是匿名函数

普通函数可以有匿名函数，也可以有具体名函数，但是箭头函数都是匿名函数。

```
// 具名函数
function func(){
  // code
}
 
// 匿名函数
let func=function(){
  // code
}

// 箭头函数全都是匿名函数
let func=()=>{
  // code
}
```

#### 箭头函数不能用于构造函数，不能被实例化

普通函数可以用于构造函数，以此创建对象实例。

#### this指向的区别

##### 箭头函数本身不创建this，但是声明时会捕获当前所在的上下文的this。

捕获的this无法改变，也就是是说call，apply，bind等方法都不能对箭头函数使用

```
var webName="捕获成功";
let func=()=>{
  console.log(this.webName);
}
func(); // 捕获成功
```

##### 普通函数的this获取的是调用它的对象，构造函数的this为创建的对象实例本身

#### 箭头函数不绑定arguments，取而代之用rest参数…解决

每一个普通函数调用后都具有一个arguments对象，用来存储实际传递的参数。但是箭头函数并没有此对象。

```
function A(a){
  console.log(arguments);
}
A(1,2,3,4,5,8);  //  [1, 2, 3, 4, 5, 8, callee: ƒ, Symbol(Symbol.iterator): ƒ]


let B = (b)=>{
  console.log(arguments);
}
B(2,92,32,32);   // Uncaught ReferenceError: arguments is not defined


let C = (...c) => {
  console.log(c);
}
C(3,82,32,11323);  // [3, 82, 32, 11323]
```

#### 其他区别

（1）箭头函数不能Generator函数，不能使用yeild关键字。
（2）箭头函数不具有prototype原型对象。
（3）箭头函数不具有super。
（4）箭头函数不具有new.target。