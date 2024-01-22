# 生命周期和组件

生命周期就是特定的时间

# mounted

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

# debugger

代码调试


# template

模板是什么

