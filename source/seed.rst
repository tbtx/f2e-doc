seed
===============

* log(msg, cat, src)

在log环境下输出log信息，避免因为忘记删除log语句而引发错误


    log(msg) =&gt; msg

    @param msg string 消息内容

    @param cat string 消息类型，如error, info, warm等
    log(msg, cat) 如log('hello', 'error')

    @param src string 消息来源
    log(msg, cat, src) 如log('hello', 'info', 'pageA') =&gt; pageA: hello

* error(msg)

抛出错误

    @param msg [string|Error]

* global

全局对象，浏览器下是window

* noop

空函数, 相当于$.noop

* mix

简单的混入