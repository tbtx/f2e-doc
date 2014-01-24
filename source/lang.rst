lang
===============

* isNotEmptyString(val)

判断是否是非空字符串

* isPlainObject(o)

相对于$.isPlainObject(), 判断一个对象是否为纯对象

* isPending(val)

判断一个deferred对象是否正在处理中

* isArray/isString/isFunction/is...

* type(o) => string/function/....
类型判断

* inArray(arr, item)

判断item是否在arr中

* isUri(val)

判断一个字符串是否是一个Uri

* singleton(fn, context)

单例模式

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

* later

延迟执行函数，对setTimeout和setInterval的一个封装

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

*  each(arr/object, fn, context)

遍历对象或数组，执行函数

    fn(item, index, arr)
    return false终止执行

* indexOf(arr, item)

数组或字符串的indeOf

* map(arr, fn, context)
* filter(arr, fn, context)
* reduce(array, callback, initialValue)

ES5 map,filter,reduce

* unique(arr)

数组去重

* sizeof(str)

返回str的长度，ascii的算1，ascii之外的算2

    expect(tbtx.sizeof("abc")).toEqual(3);
    expect(tbtx.sizeof("a汉字c")).toEqual(6);