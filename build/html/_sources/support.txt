support
===============

浏览器特性支持

tbtx.support.xx


* canvas: 是否支持canvas
* transition
* transform

* prefixed(prop) 输出带前缀的属性名

::

    tbtx.prefixed("transform") -> "WebkitTransform"

* testPropsAll(prop)

测试是否支持某属性

::

    tbtx.testPropsAll("transition") -> true/false