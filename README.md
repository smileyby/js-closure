javascript闭包（完善中...）
=============

## 闭包概念

先分析下闭包是个什么东西？

**闭包**：
> 1. 闭包就是能够读取其他函数内部变量的函数。由于在JavaScript语言中，只有函数内部的子函数能够读取局部变量，因此可以吧闭包简单理解成为“定义在一个函数内部的函数”。所以，本质上闭包就是讲函数内部和函数外部链接起来的一座桥梁。---[引自百度](https://zhidao.baidu.com/question/317091269.html)
> 
> 2. 闭包是指这样的作用域，它包含一个函数，这个函数可以调用被这个作用域所封闭的变量、函数或者闭包等内容。通常我们通过闭包所对应的函数来获得对闭包的访问。---[引自MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Closures)

## 闭包形成的原理

javascript中为什么会形成闭包？

## 闭包都能做些什么？

举例说明闭包在日常代码中的作用？

## 如何更好的理解闭包

先理解作用域，和函数

javascript 关于作用域和闭包

## 闭包使用的利与弊

### 闭包的好处

1. 缓存
2. 面向对象中的对象
3. 实现封装，防止变量跑到外层作用域中，发生命名冲突
4. 匿名自执行函数，匿名自执行函数可以减小内存消耗

http://blog.csdn.net/sunlylorn/article/details/6534610

### 闭包的坏处

1. 内存消耗

> 通常来说，函数的活动对象会随着执行上下文一起销毁，但是由于闭包引用另外一个函数的活动对象，因此这个活动函数无法销毁。这意味着，闭包比一般的函数需要更多的内训消耗。尤其是IE浏览器需要关注。由于IE使用非原生javascript对象实现dom对象，因此闭包会导致内存泄漏问题。

2. 性能问题

> 使用闭包时，会涉及到跨作用域访问，每次访问都会导致性能损失。因此在脚本中，最好小心使用闭包，它同时会涉及到内存和速度的问题。不过我们可以通过跨作用域变量存储在局部变量中，然后直接访问局部变量，来减轻对执行速度的影响。

http://blog.csdn.net/vuturn/article/details/44560717

代码中使用闭包会带来那些好处和坏处？

## 终极测试题

```js

function fun(n, o) {
	console.log(o);
	return {
		fun: function(m){
			return fun(m, n);
		}
	};
};

var a = fun(0); a.fun(1); a.fun(2); a.fun(3); // undefined,?,?,?
var b = fun(0).fun(1).fun(2).fun(3); // undefined,?,?,?
var c = fun(0).fun(1); c.fun(2); c.fun(3); // undefined,?,?,?
// 问：三行a,b,c的输出分别是什么？不要急着看答案哦

```

[我是答案](https://smileyby.github.io/js-closure/)

## 参考文章

https://zhidao.baidu.com/question/317091269.html

http://www.ruanyifeng.com/blog/2009/08/learning_javascript_closures.html

http://www.cnblogs.com/mguo/archive/2013/06/19/3143880.html

http://www.cnblogs.com/xxcanghai/p/4991870.html


