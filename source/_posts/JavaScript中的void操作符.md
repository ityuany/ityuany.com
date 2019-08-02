---
title: JavaScript中的void操作符
tags: []
abbrlink: 15721
date: 2019-08-02 11:28:14
categories:
---

![](https://ityuany.oss-cn-hangzhou.aliyuncs.com/blogs/void.jpg?x-oss-process=style/Blogs)

<!-- more -->

最近闲暇之时，看了一小段关于Babel翻译出来的代码，发现了神奇的其中一段代码如下

```JavaScript
var _object$foo;

var foo = (_object$foo = object.foo) !== null &&
          _object$foo !== void 0 ?
          _object$foo : "default";
```

十分好奇其中这么一段
```JavaScript
_object$foo !== void 0
```

查阅了相关的资料，以及动手写的几个案例，总结如下。

- void是一元运算符，出现在操作数的左边
- 操作数可以是任意类型的值
- void右边的表达式可以是带括号形式 ( 例 void(0) 或 void 0 )
- void的作用便是返回 undefined , 在它右边的操作数会正常计算，但是无论结果是什么，void都会返回undefined。
- 使用 void 0 的方式来获取 undefined 会比直接写 undefined 减少3个字节的空间占用
- undefined 在JS中并不是保留字，所以我们是可以声明 undefined 变量并且赋值的，为了避免污染，使用 void 0 来获取 undefined 会使代码更加的健壮
