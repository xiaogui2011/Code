# 生命周期和组件

## 生命周期和组件

生命周期就是特定的时间

## mounted

```js
// your-app.js

// 创建Vue实例
var app = new Vue({
  el: '#app', // 将Vue实例挂载到id为app的DOM元素上
  data: {
    message: 'Hello, Vue!'
  },
  mounted: function () {
    // 在实例挂载后执行的操作
    console.log('Vue实例已经挂载到DOM！');
    // 你可以在这里执行一些初始化的操作，例如数据的获取、DOM的操作等
  }
});

```

mounted其实就是钩子函数

## debugger

代码调试

## template

模板是什么



## html标签 / 组件元素名

区别



## 组件的嵌套

##

## vue component 构造函数

组件中this的实例

简称vc

* 数据代理
* 数据监视



## Vue实例 和 组件实例



vc diff vm

* el组件实例没资格填写

## prototype

&#x20;<img src="../.gitbook/assets/image.png" alt="" data-size="original">



## 单文件组件

什么是工作流

* webpack
* 脚手架

插件 `vutur`

\<template>不参与编译



## 暴露方式

三种方式随便挑, 一般用默认暴露



## App.Vue

汇总所有的组件



## 脚手架入口

main.js

index.js

app.js

***

index.html





