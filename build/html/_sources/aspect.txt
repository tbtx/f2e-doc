aspect
===============

使用 Aspect，可以允许你在指定方法执行的前后插入特定函数。

* before

在 object[methodName] 方法执行前，先执行 callback 函数。

* after

在 object[methodName] 方法执行后，再执行 callback 函数。

::

    var o = {};

    tbtx.classify(o);

    o.Implements(tbtx.Aspect);   // o对象即拥有了before和after方法

    或者用tbtx.Class的实例去Implements