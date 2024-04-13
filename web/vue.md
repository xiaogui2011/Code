# Vue

## Vue

JavaScript

* for each
* 遍历map
* for循环
* let

命令式编码 vs 声明式编码

虚拟DOM的diff比较

### vue之前需要掌握

es的语法规范

* 箭头函数

es6模块化

* 默认暴露
* 分别暴露
* 统一暴露
* import
* export

包管理器

* npm
* yarn
* cyarn

**原型和原型链路**

数组的常用方法

axios

promise

### 搭建Vue开发环境

装一个chrome插件, 关闭开发报警

绑定关系

```html
<div id="root">
    <h1>Hello {{name}}, 性别 {{gender}} </h1>
</div>

<script type="text/javascript">
    Vue.config.productionTip = false
    const v = new Vue({
        // el:document.getElementById("root"),
        el:"#root", // el就是把容器一起绑定起来了
        data:{ // data中用于存储数据
            name: "张三",
            gender: "男",
        }
    })
</script>
```

### MVVM

### 数据代理

参数做了数据代理， 也就是data中的内容都做了数据代理

函数没有做数据代理

## 过滤器

### js第三方的库

[BootCdn](https://www.bootcdn.cn/) 怎么使用

### 过滤器

#### 接收的参数

表面为N个， 其实是N+1个

多个过滤器的串联：就像是linux中的grep

局部过滤器filters， 全局过滤器filter

差值语法 / v-bind

### 组件

组件 一个组件就是一个微型的vm

### 内置指令

diff 自定义指令

### cookie

七天免登录的原理

为什么只输入一次账号密码

跨浏览器读取cookie是不可行的

插件 cookie editor

v-html 和 XSS攻击（冒充用户之手）

### 浏览器调试方法

<img src="../.gitbook/assets/file.excalidraw (1).svg" alt="" class="gitbook-drawing">





## 自定义指令

`Vue.directives`

自己操作DOM

只要模板一解析, 就会自动调用自定义指令



fbind

BUI(build/update/insert)

## this和箭头函数

this到底是谁
