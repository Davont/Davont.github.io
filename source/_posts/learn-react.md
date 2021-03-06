---
title: React 学习笔记
date: 2020-01-20 16:04:21
tags: [React,js]
---
# 前言
实习公司的技术栈是React-Native，得学React，再加上React本身非常流行。我记得之前去谷歌开发者大会上，有人问了一个问题，React作为前端框架，它的优势到底是什么？演讲的大牛回答：生态。好的生态，才会有未来持续变好的可能，最近几年无数的例子证明，没有优秀的生态环境，没有频繁的维护跟新，没有友好的交流社区，历史终究会把你遗忘。
## 笔记初衷
**初学，不求深刻，只求简洁。一切以接地气，大白话为主。**
# 笔记知识点
## 组件
组件就是网页上的一部分，网页整体上就是一个大组件，大组件可以继续拆分，某种意义上，HTML标签也可以称得上是组件。
React中，大写字母都是组件。
一开始引入React
```
import React from 'react'；
import ReactDOM from 'react-dom';
```
引入它的意义是让我们能够理解下面的语法（大写字母的定义之类的）
ReactDOM 是可以让组件挂载到Dom节点上。
（意思是你虽然能在网页上看到元素，但在html源代码里看不到相关元素,这是因为react是挂载dom上去的）

## react dom

react 不用直接操作dom，而是操作数据，和Vue一样，都是MVVM框架。
```
constructor(props){
    super(props);
    this.state={
        list:[
            'learn react',
            'learn english'
        ]
    }
}
```
解释：todolist 这个类刚被创建的时候，construction 会被执行，super进行初始化，不用管，stats可以存许多数据


### this.state
你想要改变数据的时候，不要直接就调用this.state 改变数据，而是用this.setState({
    list:[...this.state.list,'hello']
})

如果要操作state的数据，最好不要直接更改state上的数据，而是先拷贝一个state，然后再更改。

### react 里也有key 值 且要求不一样
### 在react中，如果你的键值和名字一样，可以直接写一个即可，如：
```
    this.setState({
      list: list
    });
```
可以修改为下面这个
```
this.setState({ list });
```

# dom理解
# 父子组件传值


* 父组件通过属性的形式向子组件传递参数，子组件通过props的形式来* 接收子组件的参数
* 子组件向父组件通信，子组件要调用父组件传递过来的方法



# 浏览器渲染

# jsx 语句
只能用js表达式，不能使用js 语句

>  JSX 语法里的并不是真正的 HTML，而是虚拟 DOM，即 JS 代码，不信可看转译后的结果

>  这种把模板直接嵌套在js语句中当表达式就是jsx语法.

>  JSX为我们提供了创建React元素方法

jsx elements必须在一个可以闭合的标签元素中
说白了react模板必须有一个父元素，并且仅有一个作为根节点。

## jsx中绑定事件

```
<button onClick={this.handleBtnClick}>add</button>
```

# 初始化react-creat-app 和以前有一些不同

一种是解释型的函数来定义，一种使用es6的class来继承。函数型的定义比较简单，语法清晰，但是不能使用state和lifecycle（或者说如果使用的话需要hook）。class继承的方式相对复杂，但可以拥有state和life
```
// 解释型的函数来定义
import React from 'react';
function App() {
  return (hello, i am veigar);
}
export default App;cycle
```
```
// 使用es6的class来继承
import React, {Component} from 'react';
class App extends Component{
  render(){
    return(hello, i am veigar)
  }
}
export default App;
```