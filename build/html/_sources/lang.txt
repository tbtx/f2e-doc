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
forEach, map, filter, every, some(fn, context) -> (object, fn, context)
同时object可以传入对象, fn的参数为(value, key, object),对于filter和map，返回的也是对象，而非数组

reduce reduceRight indexOf lastIndexOf不多说

S.each 兼容原有实现，可以循环数组或对象，在fn里return false终止


* isNotEmptyString(val)

判断是否是非空字符串

* isEmptyObject(o)

判断是否是空对象

* isPlainObject(o)

相对于$.isPlainObject(), 判断一个对象是否为纯对象

* isPending(val)

判断一个jQuery deferred对象是否正在处理中

* isArray/isString/isFunction/is...

* type(o) => string/function/....
类型判断

* inArray(arr, item)

判断item是否在arr中

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

    tbtx.ucfirst("string") => "String"

* lcfirst(val)

首字母小写

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

* sizeof(str)

返回str的长度，ascii的算1，ascii之外的算2

::

    expect(tbtx.sizeof("abc")).toEqual(3);

    expect(tbtx.sizeof("a汉字c")).toEqual(6);

* makeArray(val)

转换成一个原生数组。

* deepCopy(o)

深拷贝一个对象或数组

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

* choice(m, n)/choice(arr)

返回一个m和n之间的随机数，m和n大小随意

也可以传入一个数组，随机返回数组内一个元素

如n < m, 返回结果包含n不包含m，即tbtx.choice(0, 10)返回0-9之间的任意数

* shuffle(arr)

数组随机重排序

* Class(parent, properties)

类与继承的实现

Class的实例拥有多个方法

include(o) => 添加属性或方法到原型上，让实例调用

extend(o) => 添加类属性或方法

proxy(fn) => 保证fn调用时的this为当前class，主要用于事件处理程序

Implements(arr) => 见紧接着的classify

传入properties实际就是调用include

::

    var Slide = new Class();

    // 向类上添加静态属性

    Slide.extend({
        name: 'slide'
    });

    Slide.name =>; 'slide'

    // 向实例上添加属性,其中init方法会在实例化的时候自动调用,也可以使用Slide.fn或者prototype访问到类的原型对象

    Slide.include({
        init: funciton(page) {
            this.page = page;
        },

        sayPage: function() {
            return this.page;
        }
    });

    var s = new Slide(4);

    s.sayPage() => 4;

    // 继承
    var SpecialSlide = new Class(Slide);
    var s2 = new SpecialSlide(5);
    s2.page = 6;
    s2.sayPage() => 6

* classify(o)

让一个类或者对象（先称其为target）拥有Implements方法

Implements接受一个参数，或一个参数数组，拷贝参数原型 || 自身到 target上

::

    var o = {};

    tbtx.classify(o);

    var Events = function(){};

    Events.prototype = {

        on: function(){},

        off: function(){}

    };

    o.Implements(Events);   // o对象即拥有了on和off方法

* Now()

返回时间戳

* throttle(fn, [ms[, context]])

当在scroll事件或者resize事件里执行大量操作时，频繁触发会导致浏览器很卡，函数节流将函数限制在多少ms内只会触发一次，使用:$(window).on('resize', throttle(function, 300));

* curry(fn)

函数柯里化

调用同样的函数并且传入的参数大部分都相同的时候，就是考虑柯里化的理想场景

::

    var add = function(num1, num2) {
        return num2 + num1;
    };

    var curriedAdd = S.curry(add, 5);

    curriedAdd(3) => 8  // 5 + 3

    curriedAdd(4) => 9  // 5 + 4

* substitute(str, o, regexp)

模板替换

::

    substitute("my name is {{ name }}", {name: 'alex'}) => my name is alex

* param(o, sep, eq, serializeArray)

对象转为query字符串, =号和?号都可以自定义

* unparam(str, sep, eq)

query字符串转为对象, =号和?号都可以自定义

* escapeHtml(text)

此函数会对以下符号进行 escape： " < > & 和空格

* unEscapeHtml(text)

此函数会对以下符号进行 unEscape： " < > & 和空格