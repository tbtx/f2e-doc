lang
===============

首先实现了ES5的一些语言扩展

包括:

* Object.keys
* String.prototype.trim
* Function.prototype.bind
* Date.now
* Array.prototype.every
* Array.prototype.filter
* Array.prototype.forEach
* Array.prototype.indexOf
* Array.prototype.lastIndexOf
* Array.prototype.map
* Array.prototype.some
* Array.prototype.reduce
* Array.prototype.reduceRight
* Array.isArray

同时提供了tbtx接口，比如tbtx.trim(), tbtx.filter等等

* Object.keys(o) 对应 S.keys(o)
* Date.now 对应tbtx.Now
* fn.bind -> tbtx.bind(fn, context)
* "str".trim() -> tbtx.trim("str")

注意：
forEach, map, filter, every, some(fn, context) 相应的参数变为 (object, fn, context)

同时可以传入object和类数组对象，fn的参数为(value, key, object),对于filter和map，返回的也是对象，而非数组

reduce reduceRight indexOf lastIndexOf不多说

S.each 兼容原有实现，可以循环数组或对象，在fn里return false终止


* isNotEmptyString(val)

判断是否是非空字符串

* nextTick(fn)

在下一个浏览器空闲点执行函数，相当于setTimeout(fn, 0)

* uniqueCid()

生成客户端唯一id

* isWindow()

判断是否为window对象

* isPlainObject(o)

相对于$.isPlainObject(), 判断一个对象是否为纯对象

* extend()

jQuery extend

* isArray/isString/isFunction/is...

* type(o) => string/function/....

类型判断

* inArray(arr, item)

判断item是否在arr中

* makeArray(val)

转换成一个原生数组。

* erase(target, array)

从数组中删除元素

* singleton(fn, context)

单例模式, 多次调用返回同一实例

::

    // 唯一实例

    var getBody = tbtx.singleton(function() {
        return document.body;
    });

    getBody() === getBody() // true

    // 或者对于只执行一次的初始化函数

    var init = tbtx.singleton(function() {
        console.log("init");
        return true;
    });

    init() => init

    init() => 无输出

* ucfirst(val)

首字母大写

::

    tbtx.ucfirst("string") => "String"

* later(fn, when, periodic, context, data)

延迟执行函数，对setTimeout和setInterval的一个封装

::

    /**
     * [later description]
     * @param  {Function} fn       要执行的函数
     * @param  {number}   when     延迟时间
     * @param  {boolean}   periodic 是否周期执行
     * @param  {object}   context  context
     * @param  {Array}   data     传递的参数
     * @return {object}            timer，cancel() and interval
     */
    later: function (fn, when, periodic, context, data) {}

    var timer = tbtx.later(function(){}, 500, true);

    timer.cancel() // 取消定时器

    timer.interval => true


* unique(arr)

数组去重

* namespace(args)

命名空间，创建相应命名对象

::

    tbtx.namespace("app")

    tbtx.app => {}

* startsWith(str, prefix)

判断字符串是否以prefix开头

::

    tbtx.startsWith("abc", "a") => true

* endsWith(str, suffix)

判断字符串是否以suffix结尾

* debounce(fn, [ms[, context]])

一定间隔内没有调用时，才开始执行被调用方法。

当在scroll事件或者resize事件里执行大量操作时，频繁触发会导致浏览器很卡，使用:$(window).on('resize', debounce(function, 300));

例如很短时间内（ms内）第二次触发事件时, 不会执行fn，当停止触发ms后执行fn

* throttle(fn, [ms[, context]])

与debounce不同的是，函数节流将函数限制在多少ms内只会触发一次

* substitute(str, o, regexp)

模板替换

::

    substitute("my name is {{ name }}", {name: 'alex'}) => my name is alex

* stripTags(str)

去除html中的字符串

::

    stripTags("<p>123</p>") => 123

* stripScripts(str)

去除html中的script，包含script中的内容

::

    stripScripts("<script>var a = 123;</script>") => ""

    // 也可以指定要删除的标签
    stripScripts('<script>var a = 123;</script><style type="text/css"></style>', ["style", "script"]) => ""

* escapeHtml(text)

此函数会对以下符号进行 escape： " < > & 和空格

* unEscapeHtml(text)

此函数会对以下符号进行 unEscape： " < > & 和空格

* truncate(str, length, truncation)

对字符串进行截断，truncation默认为...