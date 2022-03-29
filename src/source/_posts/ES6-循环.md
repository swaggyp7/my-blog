title: ES6 循环
author: John Doe
tags:
  - ES6
categories:
  - Javascript
date: 2021-10-23 12:02:00
---


```
// 循环下标或者key（for-in）  
// do not actually do this
for (var index in myArray) {    
  console.log(myArray[index]);  
}  
  
// 循环value（for-of）  
for (var value of myArray) {  
  console.log(value);  
}  
  
// 甚至直接循环key和value，no problem  
for (var [key, value] of phoneBookMap) {  
  console.log(key + "'s phone number is: " + value);  
}  
```

