seed
===============

* log(msg, cat, src)

在log环境下输出log信息，避免因为忘记删除log语句而引发错误


    log(msg) =&gt; msg

    @param cat 消息类型，如error, info, warm等
    log(msg, cat) 如log('hello', 'error')

    @param src: 消息来源
    log(msg, cat, src) 如log('hello', 'info', 'pageA') =&gt; pageA: hello


* global

全局对象，浏览器下是window

* noop

空函数, 相当于$.noop

* staticUrl

静态资源地址前缀，会在后面根据tbtx.js所在目录进行重写，这里作为备用

* _tbtx

存储之前的tbtx

* debug

debug mod

* $

对jQuery或者Zepto的引用

* uniqueCid()

生成客户端唯一cid