# Vue

JavaScript

* for each
* 遍历map
* for循环
* let

命令式编码 vs 声明式编码

虚拟DOM的diff比较

## vue之前需要掌握

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

## 搭建Vue开发环境

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

## MVVM

## 数据代理

参数做了数据代理， 也就是data中的内容都做了数据代理

函数没有做数据代理


# Vue

JavaScript

* for each
* 遍历map
* for循环
* let

命令式编码 vs 声明式编码

虚拟DOM的diff比较

## vue之前需要掌握

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

## 搭建Vue开发环境

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

## MVVM

## 数据代理

参数做了数据代理， 也就是data中的内容都做了数据代理

函数没有做数据代理
