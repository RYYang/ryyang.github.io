---
layout: post
title: "prototype原型链"
author: "ryy"
---

#####javascript中的每个对象都有prototype属性，Javascript中对象的prototype属性的解释是：返回对象类型原型的引用。 
如果
obj.prototype.C=5;
那么
调用obj.C是5

如果再加一句
obj.C=3;
调用obj.C是3


想使obj.C=5

```obj.hasOwnProperty('C');//ture```

```delete obj.C;//删除自己的C```

create方法

```var obj=Object.create({x:1})：//直接创建原型链上的x```

```obj.hasOwnProperty('x');//false```

